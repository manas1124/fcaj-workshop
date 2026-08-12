---
title: "Week 7: Worklog"
date: 2026-08-03
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

## 1. Weekly Goals
Deploy automated build/deploy pipeline, integrate comprehensive monitoring with CloudWatch and X-Ray.

## 2. Detailed Work Log

| Day | Task Description | Start Date | End Date | References |
|---|---|---|---|---|
| Mon | - Configure CloudWatch Logs Insights.<br>- Install AWS X-Ray SDK in Python to measure execution time. | 03/08/2026 | 03/08/2026 | AWS Docs |
| Tue | - Create CloudWatch Alarm triggered when Lambda error exceeds 5%, integrate Alarm with SNS Topic. | 04/08/2026 | 04/08/2026 | AWS Docs |
| Wed | - Initialize AWS CodePipeline connecting to GitHub.<br>- Write `buildspec.yml` for Frontend: run `npm build` and deploy to S3. | 05/08/2026 | 05/08/2026 | AWS Docs |
| Thu | - Write `buildspec.yml` for Backend: run Unit Tests, zip libraries and source code. | 06/08/2026 | 06/08/2026 | AWS Blogs |
| Fri | - Configure `update-function-code` in CodeBuild to deploy Lambda zero-downtime.<br>- Learn basics of CloudFormation/Terraform (IaC) if time permits. | 07/08/2026 | 07/08/2026 | Weekly Report |


## 3. Achievements
- Successfully configured CloudWatch Logs Insights.
- Successfully installed AWS X-Ray SDK in Python to measure execution time.
- Successfully created CloudWatch Alarm triggered when Lambda error exceeds 5%, integrated with SNS Topic.
- Successfully initialized AWS CodePipeline connecting to GitHub.
- Successfully wrote `buildspec.yml` for Frontend: ran `npm build` and deployed to S3.
- Successfully wrote `buildspec.yml` for Backend: ran Unit Tests, zipped libraries and source code.
- Successfully configured `update-function-code` in CodeBuild for zero-downtime Lambda deployment.
- Gained basic knowledge of CloudFormation/Terraform (IaC).
- Deployed automated build/deploy pipeline with comprehensive monitoring via CloudWatch and X-Ray.

## 4. Challenges & Solutions
- **Challenges:** The research and integration process occasionally encountered unexpected errors. Required significant time reading logs and AWS technical documentation.
- **Solutions:** Coordinated with other team members for discussions, thoroughly read the guidelines, and sought additional advice from Mentors.

## 5. Plan for Next Week
- Review this week's completed work.
- Begin research and implementation of tasks for Week 8.
