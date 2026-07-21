---
title: "Week 7 Worklog"
date: 2024-01-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---



### Week 7 Objectives:

* Practice data encryption management with AWS KMS and storing sensitive info with AWS Secrets Manager.
* Deploy an API gateway with Amazon API Gateway connected to AWS Lambda.
* Brainstorm ideas for the internship project.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Watch FCJ Bootcamp KMS tutorial videos <br> - Study AWS KMS: Customer Managed Key (CMK), Key Policy, Key Rotation <br> - Practice: <br>&emsp; + Create CMK symmetric key <br>&emsp; + Encrypt/Decrypt data using KMS CLI <br>&emsp; + Enable Server-Side Encryption for S3 Bucket using KMS | 01/06/2026 | 01/06/2026 | <https://000033.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - Watch FCJ Bootcamp Secrets Manager tutorial videos <br> - Study AWS Secrets Manager: Secret types, Automatic Rotation, Version <br> - Practice: <br>&emsp; + Create Secret to store RDS connection info (username, password) <br>&emsp; + Configure 30-day Automatic Rotation <br>&emsp; + Retrieve Secret inside Lambda function using SDK <br>&emsp; + Compare Secrets Manager vs Parameter Store | 02/06/2026 | 02/06/2026 | <https://000096.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | - Watch FCJ Bootcamp API Gateway & Lambda tutorial videos <br> - Study Amazon API Gateway: REST API, HTTP API, WebSocket, Stage, Deployment <br> - Practice: <br>&emsp; + Create Lambda function (Python/Node.js) to handle requests <br>&emsp; + Create HTTP API on API Gateway connected to Lambda <br>&emsp; + Configure CORS to allow Frontend to call the API <br>&emsp; + Deploy API to Stage and test with Postman | 03/06/2026 | 04/06/2026 | <https://cloudjourney.awsstudygroup.com/> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 6   | - Attend Event (June 6th) <br> - Discuss and brainstorm internship project ideas with team | 05/06/2026 | 06/06/2026 |                                           |


### Week 7 Achievements:

* Created KMS Key and encrypted S3 data with SSE-KMS successfully.
* Securely stored and retrieved sensitive information via Secrets Manager in Lambda.
* Deployed HTTP API Gateway connected to Lambda, tested API successfully with Postman.
* Attended the Event on June 6th and proposed a project idea.

