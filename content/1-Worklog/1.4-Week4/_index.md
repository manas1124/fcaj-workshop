---
title: "Week 4: Worklog"
date: 2026-07-13
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

## 1. Weekly Goals
Build a message buffer mechanism with SQS, handle asynchronously, and send HTML emails via Amazon SES.

## 2. Detailed Work Log

| Day | Task Description | Start Date | End Date | References |
|---|---|---|---|---|
| Mon | - Create Amazon SQS Queue.<br>- Configure Dead Letter Queue (DLQ) for failed messages. | 13/07/2026 | 13/07/2026 | AWS Docs |
| Tue | - Set up EventBridge Rule to split event stream into multiple branches (Notification & Analytics). | 14/07/2026 | 14/07/2026 | AWS Docs |
| Wed | - Write `Notification Worker Lambda`, triggered directly from SQS via Event Source Mapping. | 15/07/2026 | 15/07/2026 | AWS Blogs |
| Thu | - Initialize and verify sender email address on Amazon SES. | 16/07/2026 | 16/07/2026 | AWS Docs |
| Fri | - Embed HTML template into Python, send attendance confirmation email via Amazon SES.<br>- Configure basic IAM policies for SQS and Lambda. | 17/07/2026 | 17/07/2026 | Weekly Report |


## 3. Achievements
- Successfully created Amazon SQS Queue and configured Dead Letter Queue (DLQ) for failed messages.
- Successfully set up EventBridge Rule to split event stream into Notification & Analytics branches.
- Successfully wrote Notification Worker Lambda triggered directly from SQS via Event Source Mapping.
- Successfully initialized and verified sender email address on Amazon SES.
- Successfully embedded HTML template into Python and sent attendance confirmation emails via Amazon SES.
- Successfully configured basic IAM policies for SQS and Lambda.
- Built message buffer mechanism with SQS, handled asynchronous processing, and sent HTML emails via Amazon SES.

## 4. Challenges & Solutions
- **Challenges:** The research and integration process occasionally encountered unexpected errors. Required significant time reading logs and AWS technical documentation.
- **Solutions:** Coordinated with other team members for discussions, thoroughly read the guidelines, and sought additional advice from Mentors.

## 5. Plan for Next Week
- Review this week's completed work.
- Begin research and implementation of tasks for Week 5.
