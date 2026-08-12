---
title: "Week 5: Worklog"
date: 2026-07-20
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

## 1. Weekly Goals
Integrate SNS for emergency broadcasting (SMS/email), automate cronjob to scan overdue tasks and send reminders.

## 2. Detailed Work Log

| Day | Task Description | Start Date | End Date | References |
|---|---|---|---|---|
| Mon | - Create Topic on Amazon SNS for emergency broadcasting channel (SMS/email). | 20/07/2026 | 20/07/2026 | AWS Docs |
| Tue | - Subscribe endpoints receiving system alerts to SNS Topic. | 21/07/2026 | 21/07/2026 | AWS Docs |
| Wed | - Set up Amazon EventBridge Scheduler running periodically every 30 minutes. | 22/07/2026 | 22/07/2026 | AWS Docs |
| Thu | - Write `Cronjob Worker Lambda` to scan DynamoDB for tasks about to expire. | 23/07/2026 | 23/07/2026 | AWS Blogs |
| Fri | - Integrate SES into Cronjob to automatically send reminder emails.<br>- Adjust IAM security policies for Lambda to access DynamoDB, SES, SNS. | 24/07/2026 | 24/07/2026 | Weekly Report |


## 3. Achievements
- Successfully created SNS Topic for emergency broadcasting channel (SMS/email).
- Successfully subscribed endpoints receiving system alerts to SNS Topic.
- Successfully set up Amazon EventBridge Scheduler running every 30 minutes.
- Successfully wrote Cronjob Worker Lambda to scan DynamoDB for tasks about to expire.
- Successfully integrated SES into Cronjob to automatically send reminder emails.
- Successfully adjusted IAM security policies for Lambda to access DynamoDB, SES, SNS.
- Integrated SNS for emergency broadcasting and automated cronjob for overdue task reminders.

## 4. Challenges & Solutions
- **Challenges:** The research and integration process occasionally encountered unexpected errors. Required significant time reading logs and AWS technical documentation.
- **Solutions:** Coordinated with other team members for discussions, thoroughly read the guidelines, and sought additional advice from Mentors.

## 5. Plan for Next Week
- Review this week's completed work.
- Begin research and implementation of tasks for Week 6.
