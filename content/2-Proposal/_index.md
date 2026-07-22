---
title: "Proposal"
date: 2026-06-19
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Playwright Automated Testing System using Docker on AWS

### 1. Executive Summary
The system is an End-to-End (E2E) automated testing platform for websites, designed to completely eliminate the need for engineers to manually monitor and run test suites upon every deployment change. Playwright runs inside Docker containers to simulate real user behavior on web browsers (navigation, input, verifying display outputs), followed by an AI-powered summary step that translates raw technical logs into reader-friendly summaries sent via email.
The entire system runs on AWS under an event-driven, serverless-first architecture: Amazon EventBridge triggers scheduled test runs, Amazon SQS decouples test requests from execution, an AWS Lambda function (Coordinator) initiates a standalone Amazon ECS Fargate task for each test run, and the task automatically shuts down once the report generation is complete. Consequently, the system only incurs costs for the exact minutes the tests are executing, avoiding paying for a 24/7 server that remains idle most of the time. Administrative Dashboard access is managed through Amazon Cognito, supporting role-based access control with three roles (Admin, QA/Tester, Developer).

### 2. Problem Statement
**Current Problems**
Manual E2E testing requires testers to run test scripts manually upon each deployment change, a workflow that cannot scale as the number of applications and test suites grows. There is no centralized system to schedule test runs, track historical Pass/Fail trends, or notify stakeholders automatically. Maintaining a continuous server just to be ready for the next test run generates wasted operational costs since the server remains in an idle state most of the time.

**Solution**
The system accepts two trigger sources: automated cron schedules (Amazon EventBridge) and manual on-demand triggers (Amazon API Gateway), and standardizes both into a single Amazon SQS queue coupled with a Dead Letter Queue (DLQ) to capture failed requests. An AWS Lambda function (Coordinator) consumes the queue and calls the ECS RunTask API to spin up a short-lived Amazon ECS Fargate task, running the Playwright test suite packaged in a Docker image stored in Amazon ECR. Upon completion, the task writes the HTML/JSON report to a private Amazon S3 bucket, streams real-time logs to Amazon CloudWatch, and then gracefully terminates.
A Post-processing AWS Lambda function reads the raw logs, filters out unnecessary data, and sends it to an external AI API to generate a concise natural language summary. This includes a fallback circuit-breaker mechanism to send the original report via email if the AI call fails or times out. Amazon SES handles sending the final email notification—including Pass/Fail metrics, a time-limited S3 Presigned URL, and the AI-generated summary—to the registered recipients for that application.

**Benefits and ROI**
* Eliminate manual test execution: No more manual triggers or monitoring of test results.
* Shorter feedback loops: Transforms a manual process that could take hours into an automated run lasting just a few minutes.
* Cost optimization: Pay-as-you-go pricing instead of maintaining a 24/7 server.
* Comprehensive historical storage: Every run is permanently stored in Amazon DynamoDB for quality trend analysis, which was nearly impossible when recording discretely in Excel.
* Resource liberation: Frees up QA team time to focus on designing better test scenarios instead of repeating manual testing tasks.

### 3. Solution Architecture
The system is divided into a Backend Engine (scheduling, executing, and reporting) and a Dashboard Console (UI for 3 roles: Admin, QA/Tester, Developer). All requests go through a single processing pipeline—there is no shortcut bypassing the SQS -> Lambda Coordinator -> Fargate chain, regardless of whether triggered by schedule or manually.

![Playwright automated testing solution architecture](/images/2-Proposal/Project-Page-2.drawio.png?featherlight=false&width=90pc)

**AWS Services Used**

| Service | Role in Architecture |
| --- | --- |
| Amazon EventBridge | Scheduling and generating periodic test events (cron expressions). |
| Amazon API Gateway (HTTP API) | Receiving manual trigger requests and Dashboard API calls, authenticated via Lambda Authorizer. |
| Amazon SQS + DLQ | Buffering and standardizing all test requests; DLQ stores repeatedly failing runs. |
| AWS Lambda (Coordinator) | Consuming the queue and calling ECS RunTask to initiate Fargate tasks. |
| Amazon ECS Fargate | Running the Docker/Playwright container in a Private Subnet, self-terminating upon completion. |
| Amazon ECR | Storing the Docker image containing the Playwright test runner. |
| Amazon S3 (2 buckets) | One bucket for hosting the static frontend Dashboard; a private bucket for storing reports and test artifacts. |
| Amazon CloudWatch | Collecting logs, metrics, and alerting on task timeouts or DLQ backlogs. |
| AWS Lambda (Post-processing) | Cleansing logs, calling the external AI API, and preparing notification content. |
| OpenAI API (External) | Generating natural language log summaries (replacing Amazon Bedrock due to free tier limits). |
| NAT Gateway (Public Subnet) | Allowing the Post-processing Lambda in the Private Subnet to call the external AI API. |
| Amazon SES | Sending result emails directly to registered recipients. |
| Amazon DynamoDB | Storing test history, Audit Logs, and system configuration data. |
| Amazon CloudFront | Distributing the static frontend Dashboard; combined with a CLOUDFRONT scope WAF. |
| Amazon Cognito | Authenticating Dashboard users and issuing tokens for role-based authorization. |
| AWS Secrets Manager | Storing AI API keys and other sensitive configurations. |
| Amazon VPC + VPC Endpoints (PrivateLink) | Isolating Fargate within a Private Subnet; internal AWS calls do not traverse the public Internet. |
| AWS WAF (CloudFront + Regional scopes) | Two separate Web ACLs protecting CloudFront and the API Gateway endpoint. |

**Component Design**
* Trigger Layer: Both EventBridge and API Gateway push events into the same SQS queue.
* Execution Layer: The Lambda Coordinator initiates an ECS Fargate task for each run; the task pulls the Playwright image from ECR and runs headless in a Private Subnet.
* Reporting Layer: HTML/JSON reports are saved to private S3, while logs are streamed to CloudWatch in real-time.
* AI Layer: A secondary Lambda cleans the log and calls the AI API via NAT Gateway, utilizing a circuit-breaker mechanism to fallback to the original report if the AI fails.
* Notification Layer: SES sends emails to registered application recipients, including a time-limited S3 Presigned URL.
* Access Layer: Cognito consistently enforces 3 roles (Admin, QA/Tester, Developer) at the API Gateway boundary.

### 4. Technical Implementation
**Implementation Phases**
The architecture has undergone multiple review rounds and the approach is finalized; the team is currently in the actual implementation phase, divided into the following steps:
* Phase 1. Environment & Container Setup: Configure IAM/AWS CLI, build Docker/Playwright runner (Dockerfile, entrypoint.js, playwright.config.js).
* Phase 2. Event Flow & Coordinator: Setup SQS + DLQ and Lambda Coordinator calling ECS RunTask.
* Phase 3. Storage & Monitoring: S3 (frontend + reports), CloudWatch log groups and alarms, DynamoDB tables for history and audit logs.
* Phase 4. AI Summarization: Post-processing Lambda integrating Secrets Manager for the OpenAI API key and circuit-breaker fallback mechanism.
* Phase 5. Dashboard & Authorization: Static hosting CloudFront + S3, Cognito user pool, Lambda Authorizer, and 3-role UI (Admin / QA-Tester / Developer).
* Phase 6. Security Enhancements: Least-privilege IAM policies, VPC Endpoints, and two WAF scopes (CloudFront and Regional).
* Phase 7. Integration Testing & Demo: E2E testing on a self-hosted demo website (to avoid third-party anti-bot policies), validating the entire pipeline, and preparing reports.

**Technical Requirements**
* Test Runner: Node.js, Playwright, Docker (multi-stage build) to create images pushed to ECR.
* Coordinator Logic: Use AWS SDK to call ECS RunTask from a Lambda function triggered by SQS.
* Infrastructure as Code (IaC): Recommended to provision resources using IaC (e.g., AWS CDK/CloudFormation) to ensure reproducibility across environments.
* Security Foundation: Scoped IAM roles for each component (no *FullAccess policies), Secrets Manager for credentials, and VPC Endpoints for internal service calls.

### 5. Roadmap & Milestones
**Phase 1: Self-learning AWS Fundamentals (Weeks 1–8)**
The self-learning phase for each team member. While individual learning paths varied, the team collectively acquired the necessary foundation for the workshop topic:
* AWS Foundation & Security: IAM (users, roles, policies), VPC & basic networking, Secrets Manager.
* Compute & Containerization: Docker, Amazon ECS/Fargate, Amazon ECR.
* Serverless & Event Integration: AWS Lambda, Amazon API Gateway, Amazon EventBridge, Amazon SQS.
* Storage & Data: Amazon S3, Amazon DynamoDB, Amazon CloudFront.
* Monitoring & User Authentication: Amazon CloudWatch, Amazon Cognito.
During Week 8, the team researched, referenced blogs, evaluated options, and brainstormed ideas for the workshop topic.

**Phase 2: Implementation**

| Week | Content |
| --- | --- |
| 9 | Discussed and proposed the automated testing project using Playwright. Evaluated feasibility and determined the development direction. After finalizing the topic, planned task delegation and sketched the basic architecture diagram. |
| 10 | Researched and referenced various architectural diagrams to correct errors in our drawing process. After submitting the first draft to the group for mentor feedback, several errors were identified. The team reviewed and decided to switch to a layered drawing approach for better clarity. |
| 11 | Continued refining the architecture diagram, fixing multiple errors. After the second submission, mentors approved it. With the architecture finalized, the team planned and divided implementation steps for each member. Each member prepared the necessary files and configurations for the deployment phase. |
| 12 | Upon completing preparations, members entered the deployment phase for their assigned tasks. After test-running the project, the team began finding and fixing remaining bugs, testing each function for logic errors, finally completing the workshop and starting the report writing. |

### 6. Budget Estimation
**AWS Services**

| AWS Service | Main Configuration entered in Calculator | Cost/month (USD) |
| --- | --- | --- |
| AWS Fargate | Linux/x86, 50 tasks/day, 1 min/task, 2 GB RAM, 20 GB ephemeral storage | 1.88 |
| AWS Lambda | 10,000 requests/month, 512 MB ephemeral storage | 0.00 |
| Amazon SQS | 0.0045 million standard requests/month | 0.00 |
| Amazon S3 – Frontend | 1 GB storage, 50 PUT, 1,500 GET/month | 0.03 |
| Amazon S3 – Reports | 3 GB storage, 37,500 PUT, 200 GET/month | 0.26 |
| Amazon CloudWatch | 2.2 GB log ingested, 1 dashboard, 3 standard alarms, 100 other API requests | 1.85 |
| Amazon DynamoDB (On-Demand) | 1 GB storage, 5 KB average item size | 1.88 |
| Amazon VPC – PrivateLink | 3 VPC Interface Endpoints/region | 0.05 |
| AWS Secrets Manager | 1 secret, 30 days storage, 1,500 API calls/month | 0.41 |
| Amazon Cognito | 5 MAU, Advanced Security Features enabled | 0.26 |
| Amazon CloudFront | 2,000 HTTPS requests, 1 GB data out to origin, 1 GB out to Internet | 0.11 |
| Amazon API Gateway (HTTP API) | 0.0075 million requests/month, 34 KB/request | 0.01 |
| Amazon SES | 4,500 emails sent from Lambda/month | 0.45 |
| **Subtotal (Calculator Services)** | — | **7.19** |
| NAT Gateway (Scheduled create/delete for cost optimization) | Only runs during OpenAI API calling windows, not 24/7 | 15.045 |
| **Total (Excluding OpenAI API)** | — | **22.24** |

With 22.24 USD/month, the total AWS cost over 12 months is estimated at approximately 266.82 USD (excluding the OpenAI API cost, as it is a third-party service outside the AWS Pricing Calculator and must be added manually based on actual token usage).
Important Technical Note: NAT Gateway does not support Start/Stop like EC2. To achieve the optimized cost of $15.045/month (instead of ~$43/month if running 24/7), the scheduling strategy requires using EventBridge Schedule combined with Lambda to automatically create (`CreateNatGateway`) before the execution window and delete (`DeleteNatGateway`) afterward. The trade-off is that NAT Gateway takes about 1-3 minutes to become available after creation, which may cause latency if QA triggers manual tests unexpectedly outside the scheduled window—this trade-off must be clearly stated in the risk assessment section.

### 7. Risk Assessment

| Risk | Impact | Probability |
| --- | --- | --- |
| Fargate task exceeds expected duration / timeout | Medium | Medium |
| External AI API (OpenAI) unavailable or rate-limited | Low (fallback exists) | Medium |
| IAM roles granted excessive permissions during development | High | Medium |
| Backlogged messages in DLQ without alerts | Medium | Low |
| Unexpected AWS costs due to misconfigured NAT/CloudWatch retention | Medium | Low |
| Latency when QA manually triggers tests outside NAT Gateway schedule | Medium | Medium |
| Demo website instability (if using a third-party real site) | Medium | Medium |

**Mitigation Strategies**
* Configure CloudWatch Alarms for ECS task duration and DLQ depth to detect hanging runs or repeated failures early.
* Keep the AI summarization step behind a circuit-breaker to ensure the original report is still emailed if the AI call fails.
* Apply least-privilege IAM principles from the start of deployment, rather than leaving it for later cleanup.
* Set up a DLQ -> CloudWatch Alarm -> SNS alert flow early so no silent failures are missed.
* Use a self-hosted demo website instead of real third-party domains to avoid unpredictable anti-bot measures and UI changes.
* If a manual test is triggered outside the scheduled NAT Gateway window, the system can check the NAT status before calling the AI API, or accept the 1-3 minute latency for NAT initialization. The team must agree on this approach before deployment.

**Contingency Plans**
* If the AI provider is unresponsive, the system will still email the original Pass/Fail report.
* If a Fargate task hangs, the CloudWatch alarm will trigger and the task can be force-stopped without affecting other runs (each run is independently isolated).
* If AWS costs trend unusually high, budget alerts will detect it early enough to adjust log retention or NAT usage.

### 8. Expected Outcomes
**Technical Improvements**
* Manual E2E testing is replaced by an event-driven automated pipeline with no permanent idle infrastructure.
* Role-based access control (Admin / QA-Tester / Developer) is consistently enforced at the API boundary.

**Long-term Value**
* Serves as a reusable reference architecture for future serverless, event-driven projects by the team.
* Accumulated test history data (DynamoDB) provides a foundation for analyzing recurring defects.
* Demonstrates a clear, justifiable cost model (pay-per-use) compared to traditional continuously running test servers.
