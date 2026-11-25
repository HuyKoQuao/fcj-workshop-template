---
title: "Week 9 Worklog"
date: 2026-11-16
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Finalize the capstone project topic **Driver Drowsiness & Distraction Detection** (combining Edge AI and AWS Cloud).
* Complete the system architecture design from Computer Vision processing at the Edge to storage and visualization on AWS Serverless.
* Estimate operational costs via AWS Pricing Calculator and align the proposal with mentor Lu Hoan Thien.

### Tasks Carried Out This Week:

| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| Mon | - Finalize the **Driver Drowsiness & Distraction Detection** topic <br> - Define the **Edge AI + AWS Cloud** processing approach: process webcam video directly on the Edge device to reduce latency, save bandwidth, and protect privacy, sending only event metadata to AWS | 16/11/2026 | 16/11/2026 | Project Proposal |
| Tue | - Design the processing pipeline on the Edge Device: <br>&emsp; + Use **OpenCV** + **MediaPipe Face Mesh** (478 landmarks) to extract **EAR**, **MAR**, **Head Pose**, and experiment with **Gaze Direction** <br>&emsp; + Design the **Temporal Analysis** step (rule-based + CSV analysis) and **Local Event Buffer** with a **Retry** mechanism | 17/11/2026 | 17/11/2026 | OpenCV & MediaPipe Docs |
| Wed | - Design the Serverless architecture on AWS: <br>&emsp; + Event ingestion flow: **API Gateway (HTTP API)** -> **Lambda Event Writer** -> **DynamoDB** (Conditional `PutItem` by `event_id` to prevent duplicate writes) <br>&emsp; + Dashboard viewing flow: **Amazon Cognito** (JWT) -> **API Gateway (JWT Authorizer)** -> **Lambda Event Reader** -> **DynamoDB** <br>&emsp; + Frontend: **Amazon S3 (private)** + **Amazon CloudFront (OAC)** | 18/11/2026 | 18/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> <br> <https://docs.aws.amazon.com/serverless/> |
| Thu | - Add security, monitoring, and cost estimation layers: <br>&emsp; + Manage permissions with **IAM**, monitor via **CloudWatch** & **CloudTrail**, and note **AWS WAF** as an optional extended protection component <br>&emsp; + Estimate monthly costs for serverless services using **AWS Pricing Calculator** | 19/11/2026 | 19/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> <br> <https://calculator.aws/> |
| Fri | - Present the proposal and architecture diagram <br> - Finalize remaining action items to complete: Local Event Buffer/Retry, Temporal Analysis, and testing under various lighting conditions/camera angles | 20/11/2026 | 20/11/2026 | Project Proposal |

### Week 9 Achievements:

* Completed the proposal and 10-step architecture diagram for the **Driver Drowsiness & Distraction Detection** system.
* Selected a suitable Serverless architecture to optimize costs based on actual request volume and ensure driver visual privacy.
