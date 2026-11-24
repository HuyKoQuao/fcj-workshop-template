---
title: "Week 5 Worklog"
date: 2026-10-19
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Understand how to design fault-tolerant and auto-scaling architectures using ELB and Auto Scaling.
* Configure an Application Load Balancer (ALB), Target Group, and Auto Scaling Group.
* Grasp the fundamentals of Route 53 domain routing and CloudFront CDN.

### Tasks Carried Out This Week:

| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| Mon | - Learn about **Elastic Load Balancing (ELB)**: <br>&emsp; + Compare Application Load Balancer (ALB) and Network Load Balancer (NLB) <br>&emsp; + Target Groups, Listener Rules, and Health Checks | 19/10/2026 | 19/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Tue | - Learn about **EC2 Auto Scaling**: <br>&emsp; + Launch Templates <br>&emsp; + Configure Min / Desired / Max capacity and Scaling Policies (Target Tracking) | 20/10/2026 | 20/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Wed | - Learn about **Route 53 & CloudFront**: <br>&emsp; + DNS routing policies in Route 53 (Simple, Weighted, Failover) <br>&emsp; + Edge Location caching mechanisms and CloudFront Origin Access Control (OAC) | 21/10/2026 | 21/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Thu | - **ELB & Auto Scaling Practice (Part 1):** <br>&emsp; + Create a Launch Template from a custom AMI <br>&emsp; + Create an ALB spanning 2 AZs and attach an Auto Scaling Group to the Target Group | 22/10/2026 | 22/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Fri | - **ELB & Auto Scaling Practice (Part 2):** <br>&emsp; + Run a CPU stress test to observe Auto Scaling automatically launching additional EC2 instances <br>&emsp; + Terminate a running instance to verify self-healing capabilities | 23/10/2026 | 23/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |

### Week 5 Achievements:

* Built a Multi-AZ web server cluster behind an Application Load Balancer.
* Configured and successfully tested Auto Scaling to dynamically scale server instances based on CPU load.
* Understood the roles of Route 53 and CloudFront in routing traffic and accelerating web content delivery.
