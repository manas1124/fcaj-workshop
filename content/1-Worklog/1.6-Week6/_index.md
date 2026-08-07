---
title: "Week 6 Worklog"
date: 2026-07-27
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives

* Initialize the Smart Campus Platform project using a serverless architecture.
* Build a production-ready repository structure.
* Set up Infrastructure as Code using AWS SAM and AWS CloudFormation.
* Prepare a CI/CD pipeline with GitHub Actions.

---

### Weekly Tasks

| Day       | Tasks                                                                                                          | Date       |
| --------- | -------------------------------------------------------------------------------------------------------------- | ---------- |
| Monday    | Create the GitHub repository and organize the project structure for a production-ready application.            | 27/07/2026 |
| Tuesday   | Initialize the project using AWS SAM and configure the main `template.yaml` file.                              | 28/07/2026 |
| Wednesday | Design infrastructure templates for API Gateway, Amazon Cognito, Amazon S3, DynamoDB and EventBridge.          | 29/07/2026 |
| Thursday  | Configure the development environment, install AWS CLI and AWS SAM CLI, then validate and build the project.   | 30/07/2026 |
| Friday    | Implement a GitHub Actions CI/CD pipeline including Unit Test, SAM Validate, SAM Build and SAM Deploy.         | 31/07/2026 |
| Saturday  | Verify the build and deployment workflow, review the repository structure and prepare for feature development. | 01/08/2026 |

---

### Activities

This week focused on setting up the technical foundation for the Smart Campus Platform project.

I created the GitHub repository and organized the project into a production-ready structure, including backend, infrastructure, frontend, documentation and GitHub Actions workflow directories.

Next, I initialized the project using AWS Serverless Application Model (AWS SAM) and designed the infrastructure with AWS CloudFormation templates. Infrastructure components included Amazon API Gateway, Amazon Cognito, Amazon S3, Amazon DynamoDB and Amazon EventBridge.

I then configured the local development environment, installed AWS CLI and AWS SAM CLI, and verified the infrastructure using `sam validate` and `sam build`.

Finally, I implemented a GitHub Actions pipeline to automate validation, build and deployment processes. This established a consistent deployment workflow for future development milestones.

---

### Challenges

* Learning the project structure required by AWS SAM.
* Resolving validation errors in CloudFormation templates.
* Configuring AWS credentials correctly for deployment.
* Designing a maintainable repository structure for a production-scale project.

---

### Solutions

* Studied the official AWS SAM and CloudFormation documentation.
* Modularized infrastructure into multiple CloudFormation templates.
* Verified AWS CLI configuration and IAM credentials before deployment.
* Adopted a domain-oriented repository structure with Infrastructure as Code principles.

---

### Knowledge Gained

After completing Week 6, I was able to:

* Build infrastructure using AWS SAM and CloudFormation.
* Organize a production-ready serverless repository.
* Manage infrastructure using Infrastructure as Code.
* Use `sam validate`, `sam build` and `sam deploy`.
* Build a CI/CD pipeline using GitHub Actions.

---

### Deliverables

* Smart Campus Platform repository initialized.
* Production-ready project structure completed.
* AWS SAM project configured.
* CloudFormation infrastructure templates created.
* GitHub Actions CI/CD workflow implemented.
* Initial validation, build and deployment workflow completed successfully.

---

### References

* AWS Serverless Application Model (AWS SAM) Documentation.
* AWS CloudFormation Documentation.
* GitHub Actions Documentation.
* AWS Documentation – Amazon API Gateway.
* AWS Documentation – Amazon Cognito.
* AWS Well-Architected Framework.
