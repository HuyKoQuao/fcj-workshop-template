---
title: "Week 2 Worklog"
date: 2026-09-28
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* Understand how to design an Amazon VPC virtual network and allocate IP address ranges (CIDR).
* Configure Public/Private Subnets, Route Tables, Internet Gateways, and NAT Gateways.
* Distinguish between and use Security Groups and Network ACLs (NACLs).

### Tasks Carried Out This Week:

| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| Mon | - Learn about Amazon VPC: <br>&emsp; + CIDR blocks and subnetting <br>&emsp; + Differences between Public Subnets and Private Subnets <br>&emsp; + Designing networks across multiple Availability Zones (Multi-AZ) | 28/09/2026 | 28/09/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Tue | - Learn about routing and Internet connectivity in a VPC: <br>&emsp; + Route Tables <br>&emsp; + Internet Gateway (IGW) and NAT Gateway <br>&emsp; + VPC Endpoints (Gateway & Interface) | 29/09/2026 | 29/09/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Wed | - Learn about network-level security: <br>&emsp; + Security Groups (Stateful) vs. NACLs (Stateless) <br>&emsp; + VPC Flow Logs | 30/09/2026 | 30/09/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Thu | - **Practice (Part 1):** <br>&emsp; + Create a new VPC with 2 Public Subnets and 2 Private Subnets <br>&emsp; + Attach an IGW and configure the Route Table for the Public Subnet | 01/10/2026 | 01/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| Fri | - **Practice (Part 2):** <br>&emsp; + Create a NAT Gateway to enable Internet access for EC2 instances in the Private Subnet <br>&emsp; + Test Security Group and NACL rules, and delete the NAT Gateway after completing the lab | 02/10/2026 | 02/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |

### Week 2 Achievements:

* Learned how to calculate CIDR blocks and build a complete Multi-AZ VPC architecture from scratch.
* Properly configured Route Tables, IGWs, and NAT Gateways for each subnet type.
* Gained a clear understanding of when to use Security Groups versus NACLs to allow or block traffic.
