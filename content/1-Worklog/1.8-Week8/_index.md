---
title: "Week 8 Worklog"
date: 2026-11-09
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Understand the Shared Responsibility Model and how to manage permissions using IAM Roles and JSON Policies.
* Learn how to encrypt data with AWS KMS and store credentials securely using Secrets Manager.
* Set up monitoring via CloudWatch and CloudTrail, and access EC2 instances securely using SSM Session Manager.

### Tasks Carried Out This Week:

| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| Mon | - Learn about the **AWS Shared Responsibility Model** and **AWS IAM**: <br>&emsp; + How to read and write JSON IAM Policies <br>&emsp; + Using IAM Roles for services instead of hardcoding Access Keys | 09/11/2026 | 09/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Tue | - Learn about **AWS KMS** and **AWS Secrets Manager**: <br>&emsp; + Encrypting data on EBS/S3/RDS using KMS Keys <br>&emsp; + Storing database connection strings in Secrets Manager and Parameter Store | 10/11/2026 | 10/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Wed | - Learn about server monitoring & management: <br>&emsp; + **Amazon CloudWatch** (Logs, Metrics, Alarms) and **AWS CloudTrail** (API call history) <br>&emsp; + **SSM Session Manager** (connecting to EC2 without opening port 22 or using `.pem` key files) | 11/11/2026 | 11/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Thu | - **IAM Role & Secrets Manager Practice:** <br>&emsp; + Attach an IAM Role to an EC2 instance to access S3 and retrieve database credentials from Secrets Manager <br>&emsp; + Verify access from EC2 without running `aws configure` | 12/11/2026 | 12/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Fri | - **CloudWatch & SSM Session Manager Practice:** <br>&emsp; + Create a CloudWatch Alarm to send email notifications when CPU utilization exceeds a threshold <br>&emsp; + Connect to an EC2 instance in a Private Subnet using SSM Session Manager and inspect logs in CloudTrail | 13/11/2026 | 13/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |

### Week 8 Achievements:

* Learned how to use IAM Roles and Secrets Manager to avoid hardcoding credentials in source code.
* Connected to internal EC2 instances via SSM Session Manager without exposing a public SSH port.
* Configured log monitoring and alerts on CloudWatch, and audited activity logs via CloudTrail.
