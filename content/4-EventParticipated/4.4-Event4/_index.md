---
title: "Event: 4"
date: 2026-06-27
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

# Summary Report: "Workshop on AI Agent Applications and Cloud Infrastructure Security at FCAJ Community Day"

### Event Objectives

The **FCAJ Community Day** (June 2026) was organized with the following key goals:

- **Share career insights** and hands-on experience in operating cloud infrastructure, addressing technical debt challenges in the AI era.
- **Introduce Voice AI architectures** tailored for the Vietnamese language in large enterprise environments (finance, banking).
- **Provide automation solutions** for monitoring, analyzing, and isolating system incidents through a DevOps AI Agent virtual assistant.
- **Guide the optimization of HR workflows** — from CV screening to secure talent management — using Amazon Q.
- **Present advanced technical solutions** for establishing a fully private, secure connection channel for AI Agents via the MCP Server protocol.

---

### Speakers

The workshop was structured into **5 independent sessions**, following a collaborative team presentation model, with a total of **9 speakers** (some speakers participated in two sessions):

**Session 1 – AI Applications in Cloud Infrastructure Operations & Monitoring**
- **Steve Trần** *(Founder – Cloud Thinker)*

**Session 2 – AI Voice Agent Solutions for Enterprises**
- **Hiếu Nghị** *(moderator – Renova Cloud)*
- **Kiệt** *(Live Demo – AWS Study Group)*
- **Trung** *(technical solution – Founder & CEO, R AI)*

**Session 3 – DevOps AI Agent Virtual Assistant on AWS**
- **Nguyên Nguyễn** *(theoretical foundation – Cloud Kinetic)*
- **Bảo** *(Live Demo – Cloud Kinetic)*

**Session 4 – AI-Powered Recruitment & HR Management with Amazon Q**
- **Minh Anh** *(problem framing – Noventic)*
- **Trường / Wynn** *(solution & Demo – Noventic)*

**Session 5 – Secure Private Connection Setup for Amazon Q via MCP Server**
- **Hiếu Nghị** *(moderator – Renova Cloud)*
- **Toàn Nguyễn** *(architecture & Demo – AWS Security Builder)*

---

### Key Highlights

#### Session 1 – AI Applications in Cloud Infrastructure Operations & Monitoring

*Speaker: Steve Trần (Founder – Cloud Thinker, former Solution Architect at AWS)*

Steve opened the workshop by painting a comprehensive picture of the challenges organizations face when modernizing their infrastructure:

- **Technical debt challenge:** Migrating from Monolithic systems to Microservices architecture provides scalability but significantly increases system complexity, accumulating years of "technical debt."
- **Agentic solution:** Introduced Cloud Thinker's platform, which applies AI to assist engineers in managing production infrastructure and automating code quality review (Code Review) cycles before releases.
- **Cost optimization & security:** AI-driven **FinOps** automation manages dashboards and usage measurement; hacker behavior patterns (Black/White hat) are converted into proactive security test scenarios (**Penetration Testing / Dynamic API Testing**).
- **Architecture trade-offs:** Deep discussion on **Single Agent** (handles >95% of composite tasks well) vs. **Multi-Agent** (narrows Context Windows for specialist teams, optimizes model costs, and enables effective Role-based Access Control).

---

#### Session 2 – AI Voice Agent Solutions for Enterprises

*Speakers: Hiếu Nghị (Renova Cloud) – moderator | Kiệt (AWS Study Group) – Live Demo | Trung (R AI) – technical solution*

This session addressed the unique challenges of the Vietnamese language and the architecture for solving enterprise-grade Voice AI problems:

- **Language challenge:** Vietnamese is a low-resource language, lacking large-scale training data from global corporations. Direct Speech-to-Speech models do not perform well for Vietnamese.
- **Optimal architecture:** Shifted to a **3-component pipeline**: **Speech-to-Text → LLM → Text-to-Speech**. This approach gives enterprises control over text-form output before voice synthesis, ensuring accuracy and data security (suitable for banks like VIB and VPBank).
- **Real-time optimization:** **Streaming** voice data continuously into text and feeding it directly to the LLM for immediate voice responses, eliminating waiting time.
- **Localized context handling:** Integrated an ML filter to automatically detect speaker gender (for appropriate salutation: "Anh"/"Chị") and an AI model to recognize intelligent pause patterns, preventing the agent from interrupting customers mid-sentence.
- **Live Demo:** Tested a Voice Agent built on **AWS Bedrock** combined with a **Knowledge Base** to automatically answer in English with detailed technical specifications about Apple MacBook products.

---

#### Session 3 – DevOps AI Agent Virtual Assistant on AWS

*Speakers: Nguyên Nguyễn (theoretical foundation) | Bảo (Live Demo) – Cloud Kinetic*

This session presented an automated incident response solution for DevOps/SRE engineers:

- **Real-world pain point:** When an incident occurs, telemetry data is often fragmented across multiple sources (CloudWatch, CloudTrail...). Manual lookup causes context loss, prolonging **MTTD** (Mean Time To Detect) and **MTTR** (Mean Time To Recover).
- **Six pillars of the DevOps Agent:**
  1. **Context learning** – Automatically extracts relationships between entities to generate a system Topology map via Agent Space.
  2. **Control** – Limits AI access permissions through resource Tags.
  3. **Integration** – Extends connectivity via the **MCP** (Model Context Protocol).
  4. **Collaboration** – Integrates with Slack and ServiceNow for alerting.
  5. **Convenience** – Set up directly from the AWS Console.
  6. **Cost-effectiveness** – Flexible pricing based on actual runtime (~$0.083/second).
- **4-step automated workflow:** Classify & extract logs → Investigate Root Cause (hypothesis + evidence) → Propose Mitigation Plan → Recommend long-term system improvements.
- **Live Demo:** Simulated an E-commerce application on **ECS** behind an **ALB** suffering a DDoS attack (1,000 requests/second), spiking latency to 12 seconds. The DevOps AI Agent automatically ran 5 parallel sub-tasks, identified the exact IDs of the 10 ECS Tasks spamming traffic, and generated recovery commands for engineer approval.

---

#### Session 4 – AI-Powered Recruitment & HR Management with Amazon Q

*Speakers: Minh Anh (HR problem framing) | Trường / Wynn (solution & Demo) – Noventic*

This session focused on applying AI to enterprise HR and recruitment workflows:

- **Traditional HR pain points:** Manual CV screening is time-consuming, prone to missing key talent, extends **time-to-hire**, results in subjective evaluations, and carries the risk of **data leakage** when uploading confidential CVs to public AI platforms.
- **Amazon Q solution:** An enterprise-grade secure AI assistant capable of connecting to Microsoft SharePoint, OneDrive, Google Drive, Jira, GitHub, AWS S3, and more via Actions and MCP. Internal Memory Graph management significantly reduces token consumption compared to other platforms.
- **Live Demo:** Configured AI behavior rules via a Markdown file → Amazon Q auto-generated a **Job Description** for a Cloud Engineer → Scanned a folder containing 6 candidate CVs → Cross-referenced, scored skills with percentage weights → Classified candidates (Strong / Good / Low) → Exported a detailed **HTML report** with pros/cons per candidate and estimated salary ranges.

---

#### Session 5 – Secure Private Connection Setup for Amazon Q via MCP Server

*Speakers: Hiếu Nghị (Renova Cloud) – moderator | Toàn Nguyễn (AWS Security Builder) – architecture & Demo*

The final session addressed advanced security for AI Agent systems in enterprise environments:

- **Cybersecurity risk:** When Chat Agents connect and call APIs to third-party systems (Zalo, Gmail, WhatsApp...) over the public Internet, they create significant security vulnerabilities — susceptible to **DDoS** and **Man-in-the-middle** attacks.
- **Private architecture – Zero Trust model:** All MCP Servers are placed entirely within a **VPC Private Subnet**, exposing zero attack surface to the internet.
- **Isolated data flow:**
  - Amazon Q → **Interface Endpoint (VPC Connection)** → **Route 53 Resolver** (internal DNS resolution) → **Application Load Balancer (ALB)** → MCP Server.
  - End-to-end TLS encryption using certificates from **AWS Certificate Manager (ACM)**.
  - All data remains contained within AWS cloud infrastructure.
- **Real operational cost:** Deploying advanced security components (Route 53 Resolver, dedicated ALB) incurs a fixed infrastructure cost estimated at **$250–$350/month** — organizations must evaluate the ROI vs. required security posture.
- **Live Demo:** Executed real-time query commands from the Amazon Q chat window, routing securely over the Private network to the MCP Server to inspect resources and measure system latency — completely isolated from the public internet.

---

### Key Takeaways

#### Development Mindset & System Design

- **Problem-first thinking:** AI and technology adoption must always start from solving core operational problems (security risks, technical debt, cost optimization) — not from chasing technical trends.
- **AI amplifies, not replaces, humans:** Virtual assistants (DevOps Agent, HR Agent, Voice Agent) free engineers and teams from repetitive administrative tasks. Approval authority, strategic decision-making, and handling edge cases remain entirely in human hands — the **Human-in-the-loop** model.

#### Technical Architecture & Data Governance

- **Private security and Zero Trust are non-negotiable:** For enterprise-sensitive data (financial records, HR files), always prioritize fully private connection architectures (VPC Connection, MCP Private Server) and end-to-end encryption.
- **Observability is the foundation of AI accuracy:** An AI Agent can only reason and generate accurate remediation plans if the underlying system has comprehensive logs, metrics, traces, clear alarms, and transparent deployment history. *"Poor input data → AI has no evidence to work with."*
- **Measure cost trade-offs:** Advanced security solutions carry non-trivial fixed costs — organizations must weigh ROI against their required security level before committing.

---

### Applying to Work

- **Apply to learning and projects:** Build or integrate a basic monitoring system (AWS CloudWatch) with simple AI Agents to get hands-on experience with log analysis and automated error detection workflows.
- **Optimize your resume (CV):** Knowing that HR teams now use AI (like Amazon Q) to automatically screen and rank CVs by weighted criteria — focus on writing clearly structured CVs with skills and keywords closely aligned to Job Descriptions to improve screening pass rates.
- **Practice Private network deployments:** Set up a cloud lab environment, configure an MCP Server entirely within a Private Subnet, and connect via VPC Endpoint to deeply understand routing mechanisms and internal DNS resolution.
- **Experiment with advanced AI tools:** Take advantage of free trials from technology vendors to build custom skills (using Markdown/Python files) for real tasks such as summarizing internal documents, reviewing policies, or generating automated reports to boost personal productivity.

---

### Event Experience


#### Event Photos

*Add your event photos here*
