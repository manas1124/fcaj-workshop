---
title: "Week 6: System Security with AWS WAF"
date: 2026-07-27
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

## 1. Weekly Goals
Protect API Gateway and CloudFront from common attacks, limit requests, and block access from outside the allowed scope.

## 2. Detailed Work Log

| Day | Task Description | Start Date | End Date | References |
|---|---|---|---|---|
| Mon | - Initialize AWS WAF WebACL.<br>- Attach WAF to API Gateway (Backend) and CloudFront (Frontend). | 27/07/2026 | 27/07/2026 | AWS Docs |
| Tue | - Enable AWS Managed Rules to block SQL Injection and XSS. | 28/07/2026 | 28/07/2026 | AWS Docs |
| Wed | - Create Rate-Based Rule to block IPs exceeding 1000 requests / 5 minutes. | 29/07/2026 | 29/07/2026 | AWS Docs |
| Thu | - Create Geo-Match rule to block connections from outside Vietnam territory. | 30/07/2026 | 30/07/2026 | AWS Blogs |
| Fri | - Simulate attacks and inspect WAF logs to confirm auto-block is working.<br>- Learn about AWS Shield and Certificate Manager (supplementary on roadmap). | 31/07/2026 | 31/07/2026 | Weekly Report |


## 3. Achievements
- Successfully initialized AWS WAF WebACL and attached it to API Gateway (Backend) and CloudFront (Frontend).
- Successfully enabled AWS Managed Rules to block SQL Injection and XSS attacks.
- Successfully created Rate-Based Rule to block IPs exceeding 1000 requests / 5 minutes.
- Successfully created Geo-Match rule to block connections from outside Vietnam territory.
- Successfully simulated attacks and verified auto-block functionality via WAF logs.
- Gained additional knowledge of AWS Shield and Certificate Manager.
- Protected API Gateway and CloudFront from common attacks, limited requests, and blocked access from outside the allowed scope.

## 4. Challenges & Solutions
- **Challenges:** The research and integration process occasionally encountered unexpected errors. Required significant time reading logs and AWS technical documentation.
- **Solutions:** Coordinated with other team members for discussions, thoroughly read the guidelines, and sought additional advice from Mentors.

## 5. Plan for Next Week
- Review this week's completed work.
- Begin research and implementation of tasks for Week 7.
