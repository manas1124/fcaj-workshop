---
title: "Event 1"
date: 2026-08-08
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Report: AWS AgentForge Deepdive Day 2 – Advanced Amazon Bedrock AgentCore

**Event:** Offline workshop + Hands-on Lab, 08/08/2026  
**Role:** Participant

---

## 1. Cloud/AI Career Orientation

**T-Shaped Skills** model:
- **Year 1 – Depth:** Go deep into one core specialty (serverless, data pipeline, model deployment).
- **Year 2–3 – Breadth:** Expand into production environments and build **domain knowledge** (EdTech, HealthTech, FinTech).

AWS certifications are *necessary* but not *sufficient* — solving real business problems is what keeps you in the job.  
Communication with non-technical stakeholders is a survival skill.  
Join **Hackathons** to turn theory into working products.

---

## 2. Agent Core Architecture

| | Chatbot | AI Agent |
|---|---|---|
| Output | Text only | Executes real actions |
| Capability | Q&A | Autonomous planning & acting |
| Tools | None | Calls external Tools |
| State | Stateless | Short-term & long-term Memory |

**Cognition loop:** `Reasoning` → `Thinking` → `Tool Use`. The Agent decides which tool to call and when — no hard-coded steps.

---

## 3. Memory

- **Short-term Memory:** Stores raw text within a session, processed **synchronously** — instant response but burns context window.
- **Long-term Memory:** **Memory Extraction** module runs **asynchronously** in the background, auto-extracts insights from chat and persists them.

**Trade-off:** Detailed storage → better recall but costs more tokens. Summarized storage → cheaper but may lose information.

---

## 4. Observability

Solving the "black box" problem:
- **Logging:** Records interactions and tool parameters.
- **Tracing:** Tracks the full request lifecycle to answer "why did the Agent respond that way?".
- **Metrics & Alerting:** Monitors latency, resources, traffic; connects to auto-scaling for traffic spikes.

---

## 5. Evaluation

Compare **Predicted Response** (AI-generated) against **Ground Truth** (human-authored reference) for quantitative metrics.

Cannot be 100% automated. **SMEs** must validate business accuracy, especially in healthcare and finance.

---

## 6. Policy & Security

- **Cedar Language:** Centralized declarative policy language for defining Agent permissions.
- **Permissive Mode:** Dev only.
- **Strict Mode:** Mandatory in production — enforces **Least Privilege**, prevents data leaks and destructive actions from prompt injection.

---

## 7. Extending Agent Capabilities with Tools

| Tool | Function |
|---|---|
| **Browser** | Access real-time internet data |
| **Code Interpreter** | Run code in a sandbox for calculations, charts |
| **Payment Integration** | Call payment APIs, turning the Agent into an autonomous sales assistant |

---

## 8. Hands-on Lab: Refund Assistant

**Stack:** Agent CLI + Node.js + AWS CDK (serverless deployment via CloudFormation).  
Pay-per-invoke, zero cost when idle.

Flow: user requests refund → tool looks up order → checks conditions → responds.  
**Mock Data** embedded in the System Prompt for fast logic testing, no real DB needed early on.  
**Log** kept local (dev debug), **Trace** sent to cloud observability (production monitoring).

---

## Key Takeaways

1. **Production Agent ≠ Demo Agent.** 30% is building, 70% is Memory, Observability, Evaluation, Security, and auto-scaling.
2. **Two-tier Memory:** Short-term sync (speed), long-term async (no UX slowdown).
3. **Log ≠ Trace:** Log tells you *what* happened, Trace tells you *the sequence and timing*.
4. No **Ground Truth** = blind gambling every time you tweak a prompt.
5. **Permissive** for dev, **Strict** for survival. Strict Mode check is mandatory before every release.
6. **Memory Strategy** directly impacts the token bill. Serverless is cheap for PoCs and low-traffic workloads.
7. **Career:** Depth first, breadth later. Certifications get you in, products keep you in.

## Images proving participation
![Images proving participation](/images/4-EventParticipated/event-1/event1-1.jpg)
![Images proving participation](/images/4-EventParticipated/event-1/event1-2.jpg)
![Images proving participation](/images/4-EventParticipated/event-1/event1-3.jpg)
![Images proving participation](/images/4-EventParticipated/event-1/event1-4.jpg)