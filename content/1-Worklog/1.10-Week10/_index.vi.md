---
title: "Week 10 Worklog"
date: 2026-11-23
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

* Fully deploy the project's AWS Cloud services (**DynamoDB, Cognito, Lambda, API Gateway, S3, CloudFront, CloudWatch, IAM, CloudTrail, Budgets**).
* Finalize the **Local Event Buffer & Retry** mechanism, fine-tune **Temporal Analysis**, and further evaluate **Gaze Direction** at the Edge.
* Test the entire system under various lighting conditions/camera angles and verify behavior during network disconnections.

### Tasks Carried Out This Week:

| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| Mon | - Create an **Amazon DynamoDB** table to store event metadata with `event_id` as the key <br> - Configure an **Amazon Cognito** User Pool for user registration, sign-in, and JWT issuance <br> - Create least-privilege **IAM Roles/Policies** for the Lambda functions | 23/11/2026 | 23/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> <br> <https://docs.aws.amazon.com/cognito/> |
| Tue | - Develop the **Lambda Event Writer** function to validate payloads and write to DynamoDB using Conditional `PutItem` (preventing duplicate `event_id` entries) <br> - Develop the **Lambda Event Reader** function to query event history <br> - Configure **API Gateway (HTTP API)** and attach a **JWT Authorizer** | 24/11/2026 | 24/11/2026 | <https://docs.aws.amazon.com/apigateway/> |
| Wed | - Upload the Dashboard frontend to **S3 (private)** and configure **CloudFront** using **Origin Access Control (OAC)** <br> - Enable **CloudWatch** (API access logs, Lambda logs, errors, duration, DynamoDB metrics), **CloudTrail**, and set up alert thresholds in **AWS Budgets** | 25/11/2026 | 25/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Thu | - Finalize the **Local Event Buffer** and **Retry** mechanism on the Edge device (buffering events locally during network outages and automatically resending via HTTPS POST once reconnected) <br> - Refine the **Temporal Analysis** algorithm and further evaluate the stability of **Gaze Direction** | 26/11/2026 | 26/11/2026 | OpenCV & MediaPipe Docs |
| Fri | - Test EAR, MAR, and Head Pose detection across various lighting conditions and camera angles <br> - Disconnect the network to verify local caching in the Local Event Buffer, then restore connectivity to confirm full data synchronization to DynamoDB and display on the Dashboard | 27/11/2026 | 27/11/2026 | Project GitHub Repository |

### Week 10 Achievements:

* Built the complete Serverless backend and frontend Dashboard on AWS, with JWT authentication and read/write data flows operating reliably.
* Finalized the **Local Event Buffer & Retry** mechanism, ensuring no events are lost when Internet connectivity is interrupted.
* Completed real-world testing across multiple lighting conditions, camera angles, and network fault-tolerance scenarios ahead of the submission deadline.
