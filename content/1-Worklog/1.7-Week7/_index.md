---
title: "Week 7 Worklog"
date: 2026-08-03
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives

- Complete the Smart Campus Platform according to the planned project scope.
- Deploy the serverless application to AWS using AWS SAM and AWS CloudFormation.
- Perform system testing and optimize the deployment process.
- Finalize the technical documentation, project report, and submit the final deliverables.

---

### Weekly Tasks

| Day | Tasks | Date |
|------|-------|------|
| Monday | Complete the core Lambda functions and integrate Amazon API Gateway, Amazon Cognito, Amazon S3, and Amazon DynamoDB into the application. | 03/08/2026 |
| Tuesday | Finalize the business workflows, configure IAM Roles and Amazon EventBridge, and verify the end-to-end data flow between AWS services. | 04/08/2026 |
| Wednesday | Build and deploy the infrastructure using AWS SAM, AWS CloudFormation, and GitHub Actions. Troubleshoot deployment issues and validate the infrastructure. | 05/08/2026 |
| Thursday | Perform end-to-end system testing, resolve identified issues, and optimize CloudWatch logging, IAM policies, and deployment configurations. | 06/08/2026 |
| Friday | Complete the technical documentation, update the architecture diagrams, prepare the deployment guide, and finalize the project report. | 07/08/2026 |
| Saturday | Conduct the final project review, submit the source code and documentation, and complete the project handover. | 08/08/2026 |

---

### Activities

During Week 7, I focused on completing the Smart Campus Platform before the final submission. The core functionalities of the system were fully integrated based on the AWS Serverless architecture designed in the previous weeks.

I completed the implementation of the Lambda functions responsible for face registration, attendance processing, notifications, and supporting services. The project continued to follow Clean Architecture principles by separating Lambda handlers, service logic, and shared components, making the application easier to maintain and extend.

The application was integrated with Amazon API Gateway to expose REST APIs, while Amazon Cognito was configured for authentication and authorization. Amazon S3 was used to store facial images, and Amazon DynamoDB was used to manage face metadata and attendance records. IAM Roles and IAM Policies were configured following the Principle of Least Privilege to ensure secure access to AWS resources.

After completing the application development, I deployed the infrastructure using AWS SAM and AWS CloudFormation. The deployment process was automated through GitHub Actions, including Unit Testing, SAM Validation, SAM Build, and SAM Deploy, providing a repeatable and consistent deployment workflow.

During deployment, several issues were encountered, including AWS credential configuration, SAM template validation errors, CloudFormation stack deployment failures, and IAM permission issues. These problems were resolved by reviewing AWS CLI configurations, updating SAM templates, refining IAM policies, and analyzing logs through Amazon CloudWatch.

Finally, I performed end-to-end testing of the primary business workflows, including user authentication, face registration, image storage in Amazon S3, attendance recording in Amazon DynamoDB, and communication between AWS services. After confirming that the system operated as expected, I completed the technical documentation, updated the architecture diagrams, finalized the project report, and submitted the project according to the program requirements.

---

### Challenges

- Integrating multiple AWS services into a unified serverless workflow.
- Configuring IAM Roles and IAM Policies with the appropriate permissions for each Lambda function.
- Resolving issues during `sam validate`, `sam build`, and `sam deploy`.
- Synchronizing the local development environment with the AWS cloud environment.
- Ensuring that the technical documentation accurately reflected the implemented architecture.

---

### Solutions

- Tested each AWS component independently before integrating them into the complete workflow.
- Applied the Principle of Least Privilege when configuring IAM Roles and Policies.
- Used AWS SAM validation tools before deployment to identify template issues early.
- Monitored Amazon CloudWatch logs to troubleshoot deployment and runtime errors.
- Standardized the project documentation and architecture diagrams before submission.

---

### Knowledge Gained

By the end of Week 7, I had:

- Completed a production-oriented AWS Serverless application based on the planned project scope.
- Improved my understanding of Infrastructure as Code using AWS SAM and AWS CloudFormation.
- Gained practical experience in building CI/CD pipelines with GitHub Actions.
- Strengthened my skills in integrating Amazon API Gateway, Amazon Cognito, AWS Lambda, Amazon S3, Amazon DynamoDB, Amazon EventBridge, and Amazon CloudWatch.
- Enhanced my ability to troubleshoot deployment issues and validate cloud-based applications.

---

### Deliverables

- Completed the Smart Campus Platform according to the defined project scope.
- Successfully deployed the application to AWS using AWS SAM and AWS CloudFormation.
- Implemented a functional CI/CD pipeline with GitHub Actions.
- Integrated Amazon API Gateway, Amazon Cognito, AWS Lambda, Amazon S3, Amazon DynamoDB, and Amazon EventBridge.
- Completed the technical documentation, architecture diagrams, and deployment guide.
- Submitted the final project report and source code.

---

### References

- AWS Well-Architected Framework
- AWS Serverless Application Model (AWS SAM) Documentation
- AWS CloudFormation Documentation
- AWS Lambda Developer Guide
- Amazon API Gateway Developer Guide
- Amazon Cognito Developer Guide
- Amazon DynamoDB Developer Guide
- Amazon S3 User Guide
- GitHub Actions Documentation
```