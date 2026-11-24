---
title: "Week 2 Worklog"
date: 2026-09-28
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* Understand AWS networking fundamentals and design isolated Virtual Private Clouds (VPC).
* Configure public/private subnets, route tables, Internet Gateways, and NAT Gateways.
* Implement network security layers using Security Groups and Network ACLs (NACLs).

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Learn Amazon VPC fundamentals: <br>&emsp; + CIDR blocks & IP addressing <br>&emsp; + Public Subnets vs. Private Subnets <br>&emsp; + Multi-AZ network design | 09/28/2026 | 09/28/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Learn VPC routing and gateways: <br>&emsp; + Route Tables <br>&emsp; + Internet Gateway (IGW) <br>&emsp; + NAT Gateway vs. NAT Instance <br>&emsp; + VPC Endpoints (Gateway & Interface) | 09/29/2026 | 09/29/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - Learn VPC security and traffic monitoring: <br>&emsp; + Stateful Security Groups vs. Stateless NACLs <br>&emsp; + Bastion Host architecture <br>&emsp; + VPC Flow Logs | 09/30/2026 | 09/30/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Learn hybrid & multi-VPC connectivity: <br>&emsp; + VPC Peering <br>&emsp; + AWS Transit Gateway <br>&emsp; + Site-to-Site VPN & AWS Direct Connect overview | 10/01/2026 | 10/01/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - **Practice:** <br>&emsp; + Build a custom Multi-AZ VPC from scratch <br>&emsp; + Configure IGW, NAT Gateway, and custom Route Tables <br>&emsp; + Deploy a Bastion Host in Public Subnet and test outbound internet from Private EC2 <br>&emsp; + Set up VPC Peering between two VPCs | 10/02/2026 | 10/02/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Week 2 Achievements:

* Mastered CIDR subnetting and designed a Multi-AZ VPC architecture separating public-facing and private workloads.
* Configured Internet Gateways, NAT Gateways, and custom Route Tables to control inbound and outbound network traffic.
* Differentiated and applied Security Groups and NACLs for defense-in-depth network security.
* Built and verified VPC Peering connectivity between isolated VPC environments.
