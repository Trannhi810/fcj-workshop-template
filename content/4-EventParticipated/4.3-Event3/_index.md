---
title: "Event: 3"
date: 2026-06-06
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Summary Report: "AWS Study Group Community Meetup – June 2026"

### Event Objectives

The **AWS Study Group Meetup** (June 6, 2026) was organized with the following goals:

- **Share hands-on knowledge** from community members on Cloud, DevOps, and security technologies being applied in the real world.
- **Introduce Docker** as a foundational containerization technology for Cloud and DevOps engineers.
- **Present a security solution** combining AWS WAF with Machine Learning for network intrusion detection.
- **Explore multiplayer gaming** on AWS infrastructure using WebSocket and Godot Engine.
- **Share a career journey** from IT Helpdesk to Senior Sysadmin, with a roadmap for transitioning to Cloud/DevOps.
- **Introduce AWS Neptune** for building a Graph Knowledge Base to power GraphRAG systems.
- **Discuss effective teamwork methods** in technical environments.

---

### Speakers

The meetup featured **6 speakers** presenting on distinct topics:

1. **Bảo Huỳnh** — Docker – A Containerization Technology
2. **Lê Hoàng Gia Đại** — Combining AWS WAF with Machine Learning for Cyber Attack Detection on AWS
3. **Nguyễn Quốc Bảo** — Multiplayer in the Cloud: Connecting Godot Clients with AWS WebSockets
4. **Trương Phước (Huy Phước)** — How to Work Effectively as a Team
5. **Việt Phát** — AWS Neptune for Building a Graph Knowledge Base for GraphRAG
6. **Vinh Trần** — From IT Helpdesk to Senior Sysadmin: A Self-Learning Journey and Roadmap to Cloud/DevOps

---

### Key Highlights

#### Talk 1 – Docker: A Containerization Technology

*Speaker: Bảo Huỳnh*

Docker is a containerization platform that packages an application and all its dependencies into a single, portable unit (container), ensuring consistent behavior across any environment:

- **Container vs. Virtual Machine:** Containers share the host OS kernel, consuming far fewer resources than traditional VMs while still maintaining isolation.
- **Dockerfile & Image:** The process of building an image from a Dockerfile — each instruction creates a layer, enabling efficient caching and reuse during builds.
- **Docker Compose:** Managing multiple containers simultaneously (multi-service applications) through a simple YAML configuration file.
- **DevOps applications:** Docker is an indispensable foundation in modern CI/CD pipelines and serves as the natural stepping stone toward Kubernetes (K8s) for large-scale production environments.

---

#### Talk 2 – Combining AWS WAF with Machine Learning for Cyber Attack Detection

*Speaker: Lê Hoàng Gia Đại*

This presentation introduced an intelligent Network Intrusion Detection System (NIDS) architecture on AWS:

- **Limitations of traditional WAF:** AWS WAF's rule-based approach is effective but prone to missing novel attacks (zero-days) not yet defined in its rule sets.
- **ML-NIDS solution:** Integrating a Machine Learning model to analyze traffic in real-time, detecting abnormal behavioral patterns that static rules cannot identify.
- **Data flow:** Traffic → AWS WAF → Logs → ML Model (classify: normal / attack) → Automated Alert.
- **Benefits:** Combining rule-based strength (fast, explicit) with ML adaptability (flexible, learns new patterns) creates a dual-layer defense for AWS infrastructure.

---

#### Talk 3 – Multiplayer in the Cloud: Connecting Godot Clients with AWS WebSockets

*Speaker: Nguyễn Quốc Bảo*

This talk explored building multiplayer game functionality using AWS serverless infrastructure:

- **Godot Engine:** A lightweight, open-source game engine suitable for building 2D/3D games.
- **AWS API Gateway WebSocket:** Enables persistent, bi-directional connections between client and server — unlike traditional HTTP's one-way request-response model.
- **Serverless architecture:** API Gateway WebSocket → AWS Lambda → DynamoDB (storing connection state) — no dedicated game server needed, auto-scaling with the number of players.
- **Live demonstration:** Multiple Godot clients connected simultaneously and synchronized game state in real-time via WebSocket on AWS — however, the demo encountered some technical issues during the presentation, preventing the full workflow from being shown as intended.

---

#### Talk 4 – How to Work Effectively as a Team

*Speaker: Trương Phước (Huy Phước)*

This talk focused on principles and tools that help technical teams collaborate more efficiently:

- **Clear communication:** Defining ownership, deadlines, and expectations before starting any task is critical for smooth team execution.
- **Tooling:** Platforms like Jira, Confluence, Slack, and GitHub for syncing information and tracking progress.
- **Agile/Scrum methodology:** Short sprints, daily standups, and retrospectives to detect issues early and continuously improve.
- **Feedback culture:** Building psychological safety so team members feel comfortable raising problems and offering constructive input.

---

#### Talk 5 – AWS Neptune for Building a Graph Knowledge Base for GraphRAG

*Speaker: Việt Phát*

This in-depth presentation covered applying Graph Databases to advanced RAG (Retrieval-Augmented Generation) use cases:

- **Limitations of traditional (Vector) RAG:** Semantic similarity search fails to capture structured relationships between entities.
- **What GraphRAG is:** Instead of storing documents as vectors, GraphRAG represents knowledge as a graph with nodes (entities) and edges (relationships), enabling retrieval based on complex relational context.
- **AWS Neptune:** A fully managed graph database service supporting both Gremlin and SPARQL, ideal for large-scale Knowledge Graphs.
- **Practical application:** Combining Neptune with AWS Bedrock to build an intelligent Q&A system capable of multi-hop reasoning — answering questions that require traversing multiple relationship steps.

---

#### Talk 6 – From IT Helpdesk to Senior Sysadmin: A Self-Learning Journey and Roadmap to Cloud/DevOps

*Speaker: Vinh Trần*

An inspiring career development story from within the IT industry:

- **Starting point:** Beginning from an IT Helpdesk role (basic technical support) and self-learning to reach Senior Sysadmin level within a few years.
- **Self-learning roadmap:** Combining free resources (AWS Free Tier, YouTube, official documentation), lab practice, and AWS Certifications to build a solid foundation.
- **Transitioning to Cloud/DevOps:** Linux, networking, and scripting skills from the Sysadmin era are invaluable when moving to Cloud — no need to start from scratch.
- **Practical advice:** Don't wait until you're "completely ready" to start — build real projects (portfolio), join communities (like AWS Study Group), and consistently apply knowledge in practice.

---

### Key Takeaways

#### Technical & Technology Insights

- **Containerization is a foundational skill:** Docker is not just a tool but a mindset for packaging, reusability, and environment isolation — an essential competency for any Cloud/DevOps engineer.
- **Security requires multiple layers:** No single security solution is perfect — combining rule-based (WAF) with AI/ML creates a more flexible and resilient defense system against emerging threats.
- **Serverless can truly replace traditional game servers:** WebSocket on AWS API Gateway + Lambda opens a cost-effective new approach for real-time applications at small to medium scale.
- **GraphRAG outperforms traditional RAG** for problems requiring complex relational reasoning — vector search is not always the best answer.

#### Career Mindset

- **Non-linear journeys are valid:** You don't need to start from a "prestigious" position to become a skilled Cloud engineer — what matters more is a continuous learning mindset and consistent practice.
- **Community is an invaluable asset:** Attending meetups, sharing knowledge, and learning from others' real-world experience accelerates growth far faster than self-study in isolation.
- **Teamwork is a technical skill:** Clear communication and structured workflows are just as important as coding or infrastructure skills.

---

### Applying to Work

- **Practice Docker immediately:** Containerize a personal project or learning app, write a Dockerfile, and run it with Docker Compose to understand the end-to-end workflow.
- **Lab AWS WAF security:** Set up a test web app on AWS, configure basic WAF rules, and practice reading logs to spot abnormal requests.
- **Explore WebSocket:** Build a simple chat app or real-time dashboard using AWS API Gateway WebSocket to understand bidirectional connection mechanics.
- **Plan an AWS certification path:** Inspired by Vinh Trần's journey, map out a plan to pursue AWS Cloud Practitioner or AWS Solutions Architect Associate as a clear, recognized first milestone.
- **Experiment with Graph Databases:** Try AWS Neptune or Neo4j (free Community Edition) with a small dataset to experience the difference from traditional relational databases.

---

### Event Experience

#### Event Photos

*Add your event photos here*
