---
title: "Event 2"
date: 2026-08-15
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Report: AWS AgentForge Deepdive Day 3 – AgentCore DevOps & Best Practices

**Event:** Offline workshop + Hands-on Lab, 15/08/2026  
**Role:** Participant

---

## 1. General Information

- **Duration:** 3 days (focusing on use cases, best practices, and hands-on practice on day 3)
- **Key Topics:**
  - Overview of 12 Amazon Bedrock Agent Core features (6 core + 6 auxiliary)
  - Market update: DeepSeek Harness & DeepSeek V4 Pro Max
  - Real-world use cases: DevOps (QA Testing & Bug Fixing), Visa Intelligent Commerce
  - Best practices for deploying Agentic systems in production
  - Hands-on Labs: Building an AI Agent for e-commerce using Agent Core CLI and Kiro IDE

---

## 2. Foundational Knowledge Overview

During the first two days, the program provided foundational knowledge on **Amazon Bedrock Agent Core** with 12 features divided into two groups:

- **Core Features (Agent Core):** Including Runtime, Memory, Evaluation, Observability, Browser, Code Interpreter.
- **Auxiliary Features:** Including Skill, Gateway, Identity, Harness, Payment, Sandbox/File System.

Key concepts clarified:
- **Memory:** 4 types – Reference Memory (extracting user preferences), Summary Memory (summarizing conversations), Semantic Memory (vector storage for retrieval), Episodic Memory (improving agent performance across sessions).
- **Evaluation:** 3 layers – (1) Scope/Goal: does the final result meet user needs; (2) Correctness & Fairness: is the answer accurate and unbiased; (3) Tool Usage: is the correct tool being used.
- **Observability:** Tracing, logging, and metrics via Agent Core Observability and CloudWatch, enabling performance monitoring and error detection.

---

## 3. Market Update: DeepSeek Harness & V4 Pro Max

### 3.1. DeepSeek Harness
On August 13, DeepSeek announced **Harness** – an operational framework surrounding the model layer (the "brain"), alongside the **V4 Pro Max** model.

- **Design Philosophy:** *"Everything is a plugin"* – every component outside the core model (tools, skills, sessions, sandboxes, file systems, browsers, payment gateways) can be connected, replaced, and extended like Lego bricks.
- **Architecture:** Reduces monolithic design by breaking into microservices for easier scaling and debugging.
- **Business Model:** Sells tokens via API at very low cost (demo building a 3D ISS tracking app cost only **~5 cents** for ~1 million tokens and 23 API requests).
- **Implication:** Enterprises can self-host models on on-premise hardware (e.g., RTX 5090 GPU) combined with Harness to build independent agent systems, reducing dependency on closed platforms.

### 3.2. Comparison & Lessons
- Cloud IDEs (Cursor, etc.) are moving toward closed-source, packaging premium features into paid tiers.
- DeepSeek takes the opposite approach by open-sourcing both the model and the operational framework, creating competitive advantages in cost and customization.

---

## 4. Real-World Use Cases

### 4.1. DevOps: Automated QA Testing & Bug Fixing System
**Context:** A DevOps Engineer at AWS Singapore deployed a solution to replace manual QA and bug fixing in the CI/CD pipeline.

**System Architecture:**
- **Agent 1 – QA Testing:** Uses Browser (simulating user clicks, form submissions, file uploads), Code Interpreter, Memory (Semantic + Episodic), Skills, and Observability.
- **Agent 2 – Bug Fixing:** Receives bug reports from the QA Agent, fixes code, deploys to a new branch, and creates a pull request.
- **Loop:** Developer pushes code → GitHub Actions triggers → QA Agent tests → Report by severity → Bug Fix Agent repairs → Redeploys → Retests.

**Actual Results:**
- Detected **15 bugs** in the first run, including critical issues like "Data Discrepancy" (inconsistent cost display across pages).
- **Human-in-the-loop:** The Agent does not auto-merge into production. The Senior DevOps retains the final review role, ensuring quality and correctness of fixes.

**Lesson:** Agents do not completely replace humans but act as "juniors" performing repetitive tasks, allowing seniors to focus on evaluation and decision-making.

### 4.2. Visa Intelligent Commerce – Agentic Commerce
**Context:** Visa partnered with AWS to deploy a platform for commerce between agents (agent-to-agent, agent-to-web).

**Workflow:**
1. The user's agent (e.g., chatbot) plans shopping/trips based on personal data shared via the **Data Tokens API**.
2. At payment, the agent does not directly handle card info. Instead, the user enters details into a **secure Visa popup**.
3. **Tokenization API:** Replaces the real card number with a secure 16-digit token.
4. **Authentication API & Passkey:** Biometric authentication (fingerprint/face) to confirm transactions.
5. **Signals API:** Checks each agent command (merchant, amount, purpose) before the transaction proceeds.

**Architectural Significance:**
- The agent **never holds** real payment information.
- Multi-layered security (token, cryptogram, biometric) ensures strict compliance with financial industry regulations.
- AWS Bedrock Agent Core provides safe, reliable infrastructure capable of handling Visa's scale of hundreds of billions of transactions per year.

---

## 5. Best Practices for Deploying Agentic Systems

Based on case study experiences and AWS recommendations, key best practices include:

### 5.1. Ground Truth & Evaluation
- Establish **input/output ground truth benchmarks** to measure accuracy.
- Use Agent Core's 13 built-in metrics (faithfulness, relevance, etc.) to evaluate results.
- Create multiple question variations to test agent stability.

### 5.2. Observability from Day One
- Integrate telemetry, logging, and metrics from the design phase.
- Use CloudWatch to monitor not just the agent but also underlying systems (GPU, latency).
- Set alerts for anomalies (e.g., GPU usage > 80%).

### 5.3. Break Down Monolithic Agents
- Split into specialized agents (supervisor, shopping assistant, cart manager, etc.) instead of one "do-it-all" agent.
- Easier to scale, debug, and maintain each component independently.

### 5.4. Prompt Engineering & Loop Engineering
- Optimize not just prompts but also the correct **mode** (plan mode → execute mode/agent mode).
- Plan mode typically uses a larger model for planning; execute mode uses a lighter model for execution.

### 5.5. Human-in-the-Loop
- Always keep a human in the final review step, especially for high-impact production systems (finance, healthcare).

### 5.6. UX & Latency
- End users don't care about internal architecture; they care about **response time**.
- Manage inference time by: answering simple questions first, pushing complex tasks to asynchronous background processing.
- Replace "Loading" with "Thinking" to improve user experience with AI.

### 5.7. Deterministic vs. Autonomous
- Balance deterministic flows (fixed workflows for clear processes) with autonomous behavior (agent self-decides for open-ended problems).

---

## 6. Hands-on Labs: Building an E-commerce Agent with Kiro & Agent Core

The practical portion was guided through **10 labs**, using:
- **Kiro IDE:** An AI IDE supporting code writing, steering document creation.
- **Stratosphr:** An AI framework for defining and calling LLM APIs.
- **Agent Core CLI:** Command-line tool for creating, deploying, and managing agents.
- **AWS Technologies:** Bedrock Agent Core, DynamoDB, S3 Vector Store, Lambda, API Gateway, CloudWatch.

### Lab Summary:

| Lab | Content | Knowledge Gained |
|-----|---------|------------------|
| **Lab 1** | Starter Kit & Local Web Chat | Create first agent runtime, call Bedrock LLM API, run locally with `agent-core dev` |
| **Lab 2** | System Prompt & Tools | Customize system prompt for e-commerce context (returns); define tools (lookup order, user, product) |
| **Lab 3** | Persistent Memory | Create memory with strategies (reference, summary, semantic); integrate into runtime via environment variable |
| **Lab 4** | CloudFormation Template | Deploy DynamoDB, S3 Vector Store, Bedrock Knowledge Base via infrastructure-as-code |
| **Lab 5** | Streamlit Web UI | Build web interface for agent interaction, manage users with Cognito |
| **Lab 6** | Observability & Tracing | Track token usage, latency, query CloudWatch logs; analyze real-time costs |
| **Lab 7** | Custom Features | Extend agent by adding new tools via Kiro, update tool spec |
| **Lab 8** | Harness | Centrally declare system prompt, tools, memory, gateway in one configuration set (harness) |
| **Lab 9** | Evaluation | Evaluate agent results using metrics; compare against ground truth via session ID |
| **Lab 10** | Guardrails | Set policies to control agent output content |

### Key Technical Notes from Practice:

1. **High Token Inbox vs. Outbox:**
   - When the user sends only 1-2 words (e.g., "hi"), token inbox can still reach ~1.8k.
   - **Reason:** Inbox includes not just user input but also **system prompt**, **tool definitions**, **memory context**, and chat history. This is invisible in the chat UI but still sent to the model.

2. **IAM Permissions (Machine-to-Machine):**
   - Locally, the user runs with admin rights so no extra config is needed.
   - When deploying to AWS, the **runtime** needs IAM permissions to access **memory** (and vice versa). This is service-to-service (machine-to-machine) authorization, requiring IAM policy patching.

3. **Model Cost Optimization:**
   - By default, Agent Core CLI calls Claude Sonnet (relatively expensive).
   - Switch to **Amazon Nova Lite** or **Nova Pro** via the `model.py` file to significantly reduce costs (demo showed only ~$0.2 after many hours of practice).

4. **API Gateway & Semantic Search:**
   - Agent Core Gateway is not just a proxy; it supports **semantic search** to automatically find the right tool for user requests.
   - Complete `tool spec` definitions are required so the gateway understands and routes to the correct Lambda function.

---

## 7. Personal Takeaways & Development Direction

### 7.1. Professional Knowledge
- Clear understanding that **Agent Core** is not just a "smart chatbot" but an entire ecosystem of memory, tools, evaluation, observability, and security.
- Ability to design **multi-agent systems** instead of monolithic agents, making systems easier to scale and maintain.
- Deep understanding of **security in agentic commerce**: tokenization, passkeys, and biometric authentication are mandatory, not optional.

### 7.2. Market & Technology Mindset
- AI technology is changing extremely fast (DeepSeek Harness was released just one day before the workshop).
- **Engineer's duty:** Not just understanding tools but continuously updating trends, reading papers (if research-oriented) or applying new tools (if application-oriented).
- AI deployment costs are dropping sharply: from hundreds of USD/month for closed-source to just a few cents for open-source models + self-hosting.

### 7.3. Deployment Skills
- Proficient use of **Agent Core CLI** to create resources, deploy runtimes, and add memory/knowledge bases.
- Integration of **Kiro IDE** into the development workflow to accelerate coding, create steering documents, and debug.
- Ability to read logs, trace requests, and optimize costs based on dashboards.

### 7.4. Development Direction
- **Parallel domain knowledge + technical knowledge:** You can't just be good at coding; you must understand the industry (finance, healthcare, e-commerce) to design the right solution.
- **Market monitoring:** Subscribe to tech pages, join communities to catch the latest features from AWS, DeepSeek, and other AI platforms.
- **Continuous practice:** Just 10 labs provide a complete picture of the pipeline from local development to AWS production. Need to continue applying to real projects to consolidate.

---

## 8. Conclusion

The workshop provided a comprehensive view from **theory → real-world use cases → hands-on practice** on Amazon Bedrock Agent Core. Three key takeaways were reinforced:

1. **Agent = Brain + Body:** The model is only the brain; for an agent to truly work, it needs harness, tools, memory, and execution environments (browser, code interpreter).
2. **Trust but Verify:** Always have a human in the final loop (human-in-the-loop), especially in systems affecting money and sensitive data.
3. **Cost & Speed Matter:** Good architecture is not enough if latency is high or costs exceed budget. Choosing the right model (Nova Lite/Pro instead of Claude Sonnet when possible) and designing asynchronous flows are survival factors.

With the knowledge and experience from this event, learners can confidently deploy a basic agent system on AWS while having the right vision for the development of Agentic AI technology in the near future.

## Images proving participation
![Images proving participation](/images/4-EventParticipated/event-2/event2-1.jpg)
![Images proving participation](/images/4-EventParticipated/event-2/event2-2.jpg)