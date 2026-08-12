---
title: "Week 3: Event-Driven Architecture (EventBridge)"
date: 2026-07-06
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

## 1. Weekly Goals
Deploy the Event-Driven model to reduce synchronous processing load; simultaneously consolidate knowledge of VPC and network security (Security Groups, NACLs, Internet Gateway, NAT Gateway).

## 2. Detailed Work Log

| Day | Task Description | Start Date | End Date | References |
|---|---|---|---|---|
| Mon | - Learn VPC, Security Groups, NACLs, Internet Gateway, NAT Gateway. | 06/07/2026 | 06/07/2026 | AWS Docs |
| Tue | - Initialize Custom Event Bus (`smart-campus-bus`) on Amazon EventBridge. | 07/07/2026 | 07/07/2026 | AWS Docs |
| Wed | - Build standardized JSON Event Schema (e.g., `AttendanceRecorded`) in coordination with Backend. | 08/07/2026 | 08/07/2026 | API Docs |
| Thu | - Integrate boto3 into Backend to emit event to EventBridge immediately after recording attendance. | 09/07/2026 | 09/07/2026 | AWS Blogs |
| Fri | - Define Event Rules to filter and route events.<br>- Check CloudWatch Logs to confirm successful event reception. | 10/07/2026 | 10/07/2026 | Weekly Report |


## 3. Achievements
- Gained knowledge of VPC, Security Groups, NACLs, Internet Gateway, and NAT Gateway.
- Successfully initialized Custom Event Bus (`smart-campus-bus`) on Amazon EventBridge.
- Successfully built standardized JSON Event Schema (e.g., `AttendanceRecorded`) in coordination with Backend.
- Successfully integrated boto3 into Backend to emit events to EventBridge immediately after attendance is recorded.
- Successfully defined Event Rules for filtering and routing events.
- Verified successful event reception via CloudWatch Logs.
- Deployed Event-Driven model, reducing synchronous processing load.

## 4. Challenges & Solutions
- **Challenges:** The research and integration process occasionally encountered unexpected errors. Required significant time reading logs and AWS technical documentation.
- **Solutions:** Coordinated with other team members for discussions, thoroughly read the guidelines, and sought additional advice from Mentors.

## 5. Plan for Next Week
- Review this week's completed work.
- Begin research and implementation of tasks for Week 4.
