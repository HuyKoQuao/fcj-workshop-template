---
title: "Week 3 Worklog"
date: 2026-10-05
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Understand the AWS Shared Responsibility Model and cloud security best practices.
* Implement least-privilege access control using AWS IAM Users, Groups, Roles, and JSON Policies.
* Explore AWS encryption, secrets management, and threat detection services.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Study the AWS Shared Responsibility Model <br> - Learn core AWS IAM components: <br>&emsp; + IAM Users & Groups <br>&emsp; + IAM Policies (Managed vs. Inline, JSON syntax) <br>&emsp; + Principle of Least Privilege | 10/05/2026 | 10/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Learn advanced IAM & multi-account governance: <br>&emsp; + IAM Roles & AWS STS temporary credentials <br>&emsp; + IAM Identity Center (SSO) <br>&emsp; + AWS Organizations & Service Control Policies (SCPs) | 10/06/2026 | 10/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - Learn encryption and secrets management services: <br>&emsp; + AWS Key Management Service (KMS) <br>&emsp; + AWS Secrets Manager vs. Systems Manager Parameter Store <br>&emsp; + AWS Certificate Manager (ACM) | 10/07/2026 | 10/07/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Learn auditing, compliance, and perimeter security: <br>&emsp; + AWS CloudTrail <br>&emsp; + Amazon GuardDuty & Security Hub <br>&emsp; + AWS WAF & AWS Shield | 10/08/2026 | 10/08/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - **Practice:** <br>&emsp; + Create IAM Users, Groups, and custom least-privilege JSON Policies <br>&emsp; + Attach an IAM Role to an EC2 instance to access S3 securely without hardcoded credentials <br>&emsp; + Enable CloudTrail logging and test KMS encryption | 10/09/2026 | 10/09/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Week 3 Achievements:

* Applied the AWS Shared Responsibility Model and replaced root account operations with dedicated IAM users and groups.
* Authored custom JSON IAM policies and used IAM Instance Profiles to eliminate static credentials on EC2 instances.
* Understood key management workflows with AWS KMS and secret rotation with AWS Secrets Manager.
* Configured AWS CloudTrail to audit API activities across the AWS account.
