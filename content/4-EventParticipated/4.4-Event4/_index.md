---
title: "Event: 4"
date: 2026-06-27
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

# Summary Report: "Workshop on AI Agent Applications and Cloud Infrastructure Security at FCAJ Community Day"

### Event Objectives

The **FCAJ Community Day** (June 27, 2026) was organized with the following main goals:

- **Share career insights and hands-on experience** in cloud infrastructure operations and resolving technical debt in the AI era.
- **Introduce Voice AI architectures** tailored for the Vietnamese language in enterprise environments (finance, banking).
- **Provide automation solutions** for monitoring, analyzing, and isolating system incidents using a DevOps AI Agent.
- **Guide the optimization of HR workflows** — from CV screening to talent management — using Amazon Q.
- **Present advanced technical solutions** for establishing secure, fully private connection channels for AI Agents via the MCP Server protocol.

---

### Speakers

The workshop featured **5 independent sessions** with **9 speakers**:

1. **Steve Trần** (Founder, Cloud Thinker) — AI Applications in Cloud Infrastructure Operations & Monitoring
2. **Hiếu Nghị** (Renova Cloud), **Kiệt** (AWS Study Group), **Trung** (Founder & CEO, R AI) — AI Voice Agent Solutions for Enterprises
3. **Nguyên Nguyễn** & **Bảo** (Cloud Kinetic) — DevOps AI Agent Virtual Assistant on AWS
4. **Minh Anh** & **Trường / Wynn** (Noventic) — AI-Powered Recruitment & HR Management with Amazon Q
5. **Hiếu Nghị** (Renova Cloud) & **Toàn Nguyễn** (AWS Security Builder) — Secure Private Connection Setup for Amazon Q via MCP Server

---

### Key Highlights

#### Session 1 – AI Applications in Cloud Infrastructure Operations & Monitoring

*Speaker: Steve Trần*

- **Technical debt challenge:** Migrating to Microservices provides high scalability but increases system complexity and technical debt over time.
- **Automation with AI Agent:** Applying AI to code quality review (Code Review) and automating pre-release evaluation cycles.
- **Cost optimization & FinOps:** AI-driven FinOps automatically manages dashboards and tracks resource usage to replace manual effort.
- **Single Agent vs. Multi-Agent:** Trade-offs between Single Agent (handles composite tasks well) and Multi-Agent (optimizes context windows, costs, and RBAC control).

---

#### Session 2 – AI Voice Agent Solutions for Enterprises

*Speakers: Hiếu Nghị | Kiệt | Trung*

- **Language challenge:** Vietnamese is a low-resource language where direct Speech-to-Speech models perform poorly.
- **3-component architecture:** Combining Speech-to-Text → LLM → Text-to-Speech ensures full control over text output before voice synthesis.
- **Real-time optimization:** Streaming voice data continuously into the LLM combined with gender detection and intelligent pause filters.
- **Live demonstration:** Testing a Voice Agent on AWS Bedrock integrated with a Knowledge Base for automated product specification lookup.

---

#### Session 3 – DevOps AI Agent Virtual Assistant on AWS

*Speakers: Nguyên Nguyễn | Bảo*

- **Reducing MTTD & MTTR:** Solving telemetry data fragmentation by automatically parsing logs and identifying Root Cause.
- **Six operational pillars:** Automation via Topology mapping, permission scoping with Tags, Slack/ServiceNow integration, and MCP protocol connectivity.
- **4-step workflow:** Log extraction → Root cause investigation → Mitigation proposal → Long-term system improvement recommendation.
- **Live Demo:** Simulated DDoS attack on ECS, AI Agent automatically split 5 sub-tasks, identified 10 spamming ECS tasks, and generated recovery commands.

---

#### Session 4 – AI-Powered Recruitment & HR Management with Amazon Q

*Speakers: Minh Anh | Trường / Wynn*

- **Optimizing HR workflows:** Resolving manual CV screening limitations, saving time-to-hire, and securing internal candidate data.
- **Enterprise security with Amazon Q:** Secure AI assistant connecting to SharePoint, S3, Google Drive via MCP, saving tokens using Memory Graph.
- **Recruitment automation:** Rule configuration via Markdown → Auto-generating JDs → CV scanning and scoring → Candidate classification and HTML report export.

---

#### Session 5 – Secure Private Connection Setup for Amazon Q via MCP Server

*Speakers: Hiếu Nghị | Toàn Nguyễn*

- **Public network risks:** Third-party API connections over the public Internet create DDoS and Man-in-the-middle vulnerabilities.
- **Private Zero-Trust architecture:** Hosting MCP Servers entirely within a Private Subnet, completely isolating attack surfaces from the Internet.
- **Closed data flow:** Amazon Q → VPC Interface Endpoint → Route 53 Resolver → ALB → MCP Server, with end-to-end TLS encryption via ACM.
- **Cost trade-offs:** Advanced private security infrastructure (ALB, Route 53 Resolver) incurs fixed costs ~$250–$350/month, requiring ROI evaluation.

---

### Key Takeaways

#### System Design & Security Mindset

- **Problem-first approach:** AI adoption must start from solving core security, technical debt, and cost challenges rather than chasing trends.
- **Human-in-the-loop model:** AI assistants automate repetitive tasks while humans retain strategic decision-making and approval authority.
- **Private security is top priority:** Enterprise-sensitive data requires Zero-Trust architecture and isolated private connection channels.

#### Technical Architecture & Operations

- **Importance of Observability:** AI Agents can only reason accurately when underlying systems provide quality logs, metrics, traces, and alarms.
- **Balancing cost and performance:** Carefully evaluate fixed infrastructure costs for advanced security against actual ROI value delivered.

---

### Applying to Work

- **Automated monitoring:** Integrate AWS CloudWatch with a simple AI Agent to get familiar with automated log analysis workflows.
- **Private network practice:** Set up a cloud lab environment with MCP Server in a Private Subnet connected via VPC Endpoint.
- **Explore Amazon Q & MCP:** Build knowledge bases, configure Markdown instruction files for AI Agents, and integrate internal custom actions.
- **Build custom AI skills:** Leverage AI tools to experiment with skills for automated report summarization and document review.

---

### Event Experience

FCAJ Community Day offered many practical application perspectives — from using a DevOps AI Agent to automatically detect and respond to incidents, Amazon Q automating HR recruitment workflows, to a Private Zero-Trust architecture for securing MCP Server connections. These topics helped me better understand the real complexity of enterprise AI systems and the trade-offs organizations must carefully evaluate before deployment.

#### Event Photos

![Session 1 – AgenticOps for your Cloud (Steve Trần – Cloud Thinker)](/images/4-Event/Event4/session1-agenticops-cloud-thinker.jpg?featherlight=false&width=60pc)

![Session 2 – Building Voice Agent at Scale](/images/4-Event/Event4/session2-voice-agent-at-scale.jpg?featherlight=false&width=60pc)
