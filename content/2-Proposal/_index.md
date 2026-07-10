---
title: "Proposal"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---


In this section, you need to summarize the contents of the workshop that you **plan** to conduct.

# Playwright Automation Testing Platform
## Automated Playwright Testing System using Docker on AWS

### 1. Executive Summary
The system is an End-to-End (E2E) automated testing platform for websites, built to completely eliminate the need for engineers to manually monitor and run tests every time a deployment changes. Playwright runs inside a Docker container to simulate real user behavior on a browser (navigation, data entry, checking visual results). Afterwards, an AI summarization step translates raw technical logs into easily understandable content sent via email.
The entire system operates on AWS using an event-driven, serverless-first architecture: Amazon EventBridge triggers scheduled tests, Amazon SQS decouples request intake from execution, an AWS Lambda (Coordinator) function provisions an independent Amazon ECS Fargate task for each test run, and this task automatically terminates after the report is generated. As a result, the system only incurs costs for the exact minutes the tests are actively running, rather than paying for a 24/7 server that remains idle most of the time. Access to the management Dashboard is restricted via role-based access control (Admin, QA/Tester, Developer) powered by Amazon Cognito.

### 2. Problem Statement
*Current Problem*
Manual E2E testing requires testers to manually execute test scripts every time a change is deployed. This approach cannot scale as the number of applications and test cases grows. There is no centralized system to schedule tests, track Pass/Fail trends over time, or automatically notify the relevant stakeholders. Maintaining a continuously running server just to be ready for the next test run wastes operational costs because the server remains idle for the vast majority of the time.

*The Solution*
The system receives triggers from two sources: scheduled cron jobs (Amazon EventBridge) and manual on-demand requests (Amazon API Gateway). Both are standardized into a common Amazon SQS queue, which includes a Dead Letter Queue (DLQ) to capture failed processing requests. An AWS Lambda (Coordinator) function acts as the queue consumer, calling the RunTask API to launch a short-lived Amazon ECS Fargate task. This task runs the Playwright test suite, which is packaged in a Docker image stored in Amazon ECR. Upon completion, the task writes the HTML/JSON report to a private Amazon S3 bucket, streams real-time logs to Amazon CloudWatch, and then automatically shuts down.
A post-processing AWS Lambda function reads the raw logs, filters out unnecessary data, and sends it to an external AI API to generate a short, natural language summary. It includes a fallback (circuit-breaker) mechanism to send the original report via email if the AI API fails or times out. Amazon SES handles sending the final notification email—containing the Pass/Fail metrics, a time-limited S3 Presigned URL, and the AI-generated summary—to the precise mailing list registered for that application.

*Benefits and Return on Investment (ROI)*
- Eliminates manual test execution: No more manual triggers or waiting for results.
- Shortens feedback loop: Transforms a manual process that could take hours into an automated run taking just minutes.
- Cost optimization: Costs are incurred based on actual usage rather than maintaining a 24/7 server.
- Comprehensive historical storage: Every test run is permanently stored in Amazon DynamoDB, enabling quality trend analysis—something nearly impossible with disjointed Excel logs.
- Frees up the QA team's time to focus on designing better test cases rather than repeating mundane manual testing tasks.

### 3. Solution Architecture
The system is divided into the Backend Engine (scheduling, execution, and test reporting) and the Dashboard Console (UI tailored for 3 roles: Admin, QA/Tester, Developer). All requests go through a single, standardized processing pipeline—SQS -> Lambda Coordinator -> Fargate—with no shortcuts, whether triggered by schedule or manually.

![Architecture](/images/2-Proposal/Project-Page-2.drawio.png)

*AWS Services Used*
- **Amazon EventBridge**: Schedules and generates recurring test events (cron expressions).
- **Amazon API Gateway (HTTP API)**: Receives manual trigger requests and API calls from the Dashboard, authenticated via Lambda Authorizer.
- **Amazon SQS + DLQ**: Buffers and standardizes all test requests; the DLQ stores repeatedly failed runs.
- **AWS Lambda (Coordinator)**: Consumes the queue and calls ECS RunTask to launch Fargate tasks.
- **Amazon ECS Fargate**: Runs the Docker/Playwright container in a Private Subnet, automatically terminating upon completion.
- **Amazon ECR**: Stores the Docker image containing the Playwright test runner.
- **Amazon S3 (2 buckets)**: One bucket hosts the static frontend Dashboard; a private bucket stores reports and test files.
- **Amazon CloudWatch**: Collects logs, metrics, and triggers alarms if a task exceeds its time limit or if the DLQ backs up.
- **AWS Lambda (Post-processing)**: Cleans logs, calls the external AI API, and prepares the notification content.
- **OpenAI API (External to AWS)**: Generates natural language summaries of the logs (replacing Amazon Bedrock due to free tier limitations).
- **NAT Gateway (Public Subnet)**: Allows the Post-processing Lambda in the Private Subnet to call the external AI API.
- **Amazon SES**: Sends result emails directly to registered recipients.
- **Amazon DynamoDB**: Stores test history, Audit Logs, and system configuration data.
- **Amazon CloudFront**: Distributes the static frontend Dashboard; integrated with a CLOUDFRONT-scoped WAF.
- **Amazon Cognito**: Authenticates Dashboard users and issues tokens for role-based access control.
- **AWS Secrets Manager**: Stores the AI API key and other sensitive configurations.
- **Amazon VPC + VPC Endpoints (PrivateLink)**: Isolates Fargate within a Private Subnet; internal AWS API calls do not traverse the public Internet.
- **AWS WAF (CloudFront & Regional Scopes)**: Two separate Web ACLs protect CloudFront and the API Gateway endpoint.

*Component Design*
- **Trigger Layer**: Both EventBridge and API Gateway push events into the same SQS queue.
- **Execution Layer**: The Lambda Coordinator launches one ECS Fargate task per run. The task pulls the Playwright image from ECR and runs headlessly in a Private Subnet.
- **Reporting Layer**: HTML/JSON reports are stored in a private S3 bucket, while logs are streamed to CloudWatch in real-time.
- **AI Layer**: A secondary Lambda cleans the logs and calls the AI API via a NAT Gateway, utilizing a circuit-breaker to fallback to the original report if the AI fails.
- **Notification Layer**: SES sends an email to the registered recipients for the app, including a time-limited S3 Presigned URL.
- **Access Layer**: Cognito consistently enforces the 3 roles (Admin, QA/Tester, Developer) at the API Gateway boundary.

### 4. Technical Implementation
*Implementation Phases*
The architecture has gone through multiple review rounds and the approach is finalized; the team is currently in the actual implementation phase, broken down as follows:
1. **Phase 1: Environment & Container Setup**: Configure IAM/AWS CLI, and build the Docker/Playwright runner (Dockerfile, entrypoint.js, playwright.config.js).
2. **Phase 2: Event Workflow & Coordinator**: Set up SQS + DLQ and the Lambda Coordinator to call ECS RunTask.
3. **Phase 3: Storage & Monitoring**: S3 (frontend + reports), CloudWatch log groups and alarms, DynamoDB tables for history and audit logs.
4. **Phase 4: AI Summarization**: Post-processing Lambda integrated with Secrets Manager for the OpenAI API key, including the circuit-breaker fallback mechanism.
5. **Phase 5: Dashboard & Access Control**: CloudFront + S3 static hosting, Cognito user pool, Lambda Authorizer, and the 3-role UI (Admin / QA-Tester / Developer).
6. **Phase 6: Security Enhancements**: Strict least-privilege IAM policies, VPC Endpoints, and dual WAF scopes (CloudFront and Regional).
7. **Phase 7: Integration Testing & Demo**: Run end-to-end tests on a self-hosted demo website (to avoid third-party anti-bot policies), validate the entire pipeline, and prepare the final report.

*Technical Requirements*
- Test Runner: Node.js, Playwright, Docker (multi-stage build) to create and push the image to ECR.
- Coordinator Logic: Use the AWS SDK to call ECS RunTask from a Lambda function triggered by SQS.
- Infrastructure as Code (IaC): Recommended to provision resources using IaC (e.g., AWS CDK/CloudFormation) to ensure reproducibility across environments.
- Security Foundation: IAM roles limit the scope for each component (avoiding *FullAccess policies), Secrets Manager handles credentials, and VPC Endpoints secure internal service calls.

### 5. Timeline & Milestones
- **Month 1**: Initialize infrastructure, set up the AWS environment, configure IAM Roles, and build the core Playwright Docker runner.
- **Month 2**: Deploy the serverless architecture with API Gateway, SQS, EventBridge, and Fargate. Develop the Backend logic using Lambda. Set up S3 for report storage.
- **Month 3**: Integrate AI Post-processing, configure Cognito, and develop the Frontend Dashboard. Finalize VPC and WAF security, and conduct system-wide End-to-End testing.

### 6. Budget Estimation
| AWS Service | Main Configuration (AWS Calculator) | Cost/month (USD) |
|---|---|---|
| **AWS Fargate** | Linux/x86, 50 tasks/day, 1 min/task, 2 GB RAM, 20 GB ephemeral storage | 1.88 |
| **AWS Lambda** | 10,000 requests/month, 512 MB ephemeral storage | 0.00 |
| **Amazon SQS** | 0.0045 million standard requests/month | 0.00 |
| **Amazon S3 – Frontend** | 1 GB storage, 50 PUT, 1,500 GET/month | 0.03 |
| **Amazon S3 – Reports** | 3 GB storage, 37,500 PUT, 200 GET/month | 0.26 |
| **Amazon CloudWatch** | 2.2 GB log ingested, 1 dashboard, 3 standard alarms, 100 other API requests | 1.85 |
| **Amazon DynamoDB (On-Demand)** | 1 GB storage, average item size 5 KB | 1.88 |
| **Amazon VPC – PrivateLink** | 3 VPC Interface Endpoints/region | 0.05 |
| **AWS Secrets Manager** | 1 secret, 30 days retention, 1,500 API calls/month | 0.41 |
| **Amazon Cognito** | 5 MAUs, Advanced Security Features enabled | 0.26 |
| **Amazon CloudFront** | 2,000 HTTPS requests, 1 GB data to origin, 1 GB to Internet | 0.11 |
| **Amazon API Gateway (HTTP API)** | 0.0075 million requests/month, 34 KB/request | 0.01 |
| **Amazon SES** | 4,500 emails sent via Lambda/month | 0.45 |
| **Subtotal (Calculator Services)** | — | **7.19** |
| **NAT Gateway** (scheduled creation/deletion) | Runs only during OpenAI API calling window, not 24/7 | **15.045** |
| **Total (excluding OpenAI API)** | — | **22.24** |

At $22.24 USD/month, the total AWS cost over 12 months is estimated at around $266.82 USD (excluding the OpenAI API cost, as it is a third-party service outside the AWS Pricing Calculator and must be added manually based on the provider's token pricing).

*Critical Technical Note*: NAT Gateway does not support Start/Stop like EC2. To achieve an optimal cost of $15.045 USD/month (instead of ~$43 USD/month if running 24/7), the scheduling approach requires using EventBridge Schedules and Lambda to automatically create (CreateNatGateway) before the required time window and delete (DeleteNatGateway) afterward. The trade-off is that NAT Gateway takes about 1-3 minutes to become ready after creation, which could cause latency if QA manually triggers an ad-hoc test outside the scheduled window—this trade-off must be clearly stated in the risk section of the report.

### 7. Risk Assessment
*Risk Matrix*
- **Fargate task exceeds expected time / timeouts**: Medium impact, Medium probability.
- **External AI API (OpenAI) unavailable or rate-limited**: Low impact, Medium probability.
- **IAM roles granted excessive permissions during development**: High impact, Medium probability.
- **Messages stuck in DLQ without alerts**: Medium impact, Low probability.
- **AWS costs exceed budget**: Medium impact, Low probability.
- **Latency when QA manually triggers tests outside the scheduled NAT Gateway window**: Medium impact, Medium probability.

*Mitigation Strategies*
- Set up CloudWatch Alarms for ECS task duration and DLQ depth to quickly detect hanging tasks or recurring failures.
- Place the AI summarization step behind a circuit-breaker so the original report is still emailed if the AI call fails.
- Apply least-privilege IAM principles from the start of deployment, rather than leaving it for later cleanup.
- Set up the DLQ -> CloudWatch Alarm -> SNS alert flow early so no silent failures go unnoticed.
- If a test is triggered manually outside the NAT Gateway scheduled window, the system can check the NAT status before calling the AI API, or accept a 1-3 minute delay for NAT initialization. This approach must be agreed upon by the team prior to deployment.

*Contingency Plans*
- If the AI provider does not respond, the system will fallback to sending the original Pass/Fail report via email.
- If a Fargate task hangs, the CloudWatch alarm will trigger, and the task can be forcefully stopped without affecting other runs (since each run is isolated).
- If AWS costs trend unusually high, budget alerts will trigger early enough to adjust log retention times or NAT usage.

### 8. Expected Outcomes
*Technical Improvements*: Manual E2E testing is replaced with an event-driven automated pipeline, eliminating idle infrastructure. Role-based access control (Admin / QA-Tester / Developer) is consistently enforced at the API boundary.
*Long-term Value*: Serves as a reference architecture that can be reused for future serverless, event-driven projects within the team. The accumulated historical test data (in DynamoDB) lays the foundation for future analysis of recurring errors. Demonstrates a clear, justifiable cost model (pay-per-use) compared to traditional continuously running test servers.