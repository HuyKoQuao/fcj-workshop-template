---
title: "Proposal"
date: 2026-11-16
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Driver Drowsiness & Distraction Detection
## A Driver Drowsiness and Distraction Detection System Combining Edge AI and AWS Serverless

### 1. Problem & Solution Overview

**Driver Drowsiness & Distraction Detection** is a monitoring system designed for early detection of driver drowsiness or distraction during driving by combining **Computer Vision** with **AWS Cloud**, aiming to improve road safety awareness and reduce potential accident risks.

Instead of continuously streaming raw video to the cloud for processing, the system adopts a hybrid **Edge AI + AWS Serverless** architecture:
* **At the Edge Device:** Facial video frames captured from a webcam are processed locally using **OpenCV** and **MediaPipe Face Mesh** to extract behavioral features and analyze states over time. Raw video is never transmitted outside the device.
* **On the AWS Cloud Platform:** Only **metadata** of anomalous events is sent to AWS via **Amazon API Gateway** and **AWS Lambda** for validation, deduplication, storage in **Amazon DynamoDB**, and historical visualization on a Dashboard (**Amazon S3 + CloudFront**) secured by **Amazon Cognito**.

---

### 2. Objectives & Scope

**Project Objectives**
* Build an on-device computer vision pipeline at the edge to extract facial state metrics including **EAR** (*Eye Aspect Ratio*), **MAR** (*Mouth Aspect Ratio*), **Head Pose**, and experimental **Gaze Direction**.
* Apply time-series analysis (**Temporal Analysis**) to accurately identify signs of drowsiness or distraction while minimizing false positives.
* Deploy a lightweight, secure, and cost-optimized **AWS Serverless** backend infrastructure to ingest, store, and query event history.
* Ensure continuous system reliability even during internet outages through a **Local Event Buffer** and automatic **Retry** mechanism.

**Project Scope**
* **Edge AI Processing:** Capture webcam frames, detect 478 facial landmarks, extract behavioral features, and classify states using a rule-based engine combined with CSV analysis. The **Gaze Direction** component remains experimental and requires further evaluation before being used as a primary detection criterion.
* **AWS Cloud Infrastructure:** Implement a complete Serverless stack comprising **API Gateway (HTTP API)**, **AWS Lambda** (Event Writer & Event Reader), **Amazon DynamoDB**, **Amazon Cognito**, **Amazon S3 (private)**, **Amazon CloudFront (OAC)**, **Amazon CloudWatch**, **AWS IAM**, **AWS CloudTrail**, and **AWS Budgets** (along with **AWS WAF** as an optional edge-protection layer).
* **Testing & Evaluation:** Evaluate detection accuracy across varying lighting conditions and camera angles, and verify data synchronization resilience during network disconnection and recovery.

---

### 3. Problems to Solve

* **Delayed recognition of drowsiness and distraction cues:** Behavioral signs such as prolonged eye closure, frequent yawning, head posture shifts, or gaze deviation occur rapidly, making it difficult for drivers to self-monitor without continuous automated tracking.
* **Limitations of centralized cloud video processing:** Streaming real-time video to the cloud demands high network bandwidth, increases response latency, drives up infrastructure costs, and introduces privacy risks regarding driver footage.
* **Data loss or duplication under unstable network conditions:** Devices operating inside moving vehicles frequently experience intermittent connectivity. Without local buffering and unique event identification, alert records can be lost or duplicated upon retransmission.

---

### 4. Preliminary Solution Architecture

![Driver Drowsiness & Distraction Detection Architecture](/images/2-Proposal/system_architecture.png)

#### 10-Stage System Processing Flow

1. **Data Acquisition:** A webcam captures the driver's facial frames and feeds them directly into the local Edge processor (no video is uploaded to AWS).
2. **Edge AI Processing:** **OpenCV** combined with **MediaPipe Face Mesh** (478 landmarks) extracts **EAR**, **MAR**, **Head Pose**, and experimental **Gaze Direction** metrics.
3. **State Analysis:** Extracted features pass through **Temporal Analysis** (using CSV analysis and rule-based candidates) to evaluate drowsiness or distraction states over time.
4. **Local Event Buffering:** Upon detecting an event, the system generates a unique `event_id` and stores the metadata in the **Local Event Buffer**. A **Retry** mechanism automatically resends unsynced events if network connectivity drops.
5. **Cloud Ingestion:** The device transmits the event metadata payload via **HTTPS POST** to **Amazon API Gateway (HTTP API)**.
6. **Event Validation & Persistence:** API Gateway routes the request to the **AWS Lambda Event Writer** function to validate the payload. Lambda then executes a **Conditional `PutItem`** operation in **Amazon DynamoDB** keyed by `event_id` to prevent duplicate entries.
7. **Authentication & Authorization:** The Dashboard uses **Amazon Cognito** to handle user sign-up, sign-in, and **JWT** issuance. **API Gateway** uses a **JWT Authorizer** to verify access permissions on incoming requests.
8. **History Querying:** When a user views event history on the Dashboard, the authenticated request passes through API Gateway to the **AWS Lambda Event Reader** function to query records from DynamoDB.
9. **Dashboard Delivery:** The frontend application is hosted on a private **Amazon S3** bucket and delivered globally via **Amazon CloudFront** configured with **Origin Access Control (OAC)**.
10. **System Monitoring:** **Amazon CloudWatch** collects API access logs, Lambda logs, error rates, execution durations, and DynamoDB metrics for operational observability and anomaly alerting.

#### Summary of AWS Services Used

| Functional Group | AWS Services | Role in Architecture |
| --- | --- | --- |
| **API Ingestion & Compute** | Amazon API Gateway (HTTP API), AWS Lambda | Ingests events from the Edge Device, enforces JWT authorization, and executes write/read logic (`Event Writer` & `Event Reader`). |
| **Data Storage** | Amazon DynamoDB | Stores event metadata centrally and guarantees idempotency via Conditional `PutItem` on `event_id`. |
| **Frontend & Content Delivery** | Amazon S3 (private), Amazon CloudFront (OAC) | Securely hosts static web assets and delivers the Dashboard UI over HTTPS. |
| **Authentication & Security** | Amazon Cognito, AWS IAM, AWS WAF *(Optional)* | Manages user accounts and JWT tokens, enforces least-privilege service permissions, and protects the API perimeter. |
| **Monitoring & Cost Control** | Amazon CloudWatch, AWS CloudTrail, AWS Budgets | Collects logs and metrics, audits account API activity, and triggers alerts on spending thresholds. |

---

### 5. Implementation Plan & Timeline

The project execution roadmap aligns with the 11-week internship schedule (**September 21, 2026 – November 30, 2026**):

* **Phase 1 – AWS Foundations & Core Edge Pipeline (Weeks 1 – 8 | Sep 21, 2026 – Nov 13, 2026):**
  * Gain hands-on proficiency in core AWS services (VPC, EC2, S3, DynamoDB, IAM, CloudWatch) and Serverless design patterns.
  * Build the initial Edge processing pipeline using a webcam, OpenCV, MediaPipe Face Mesh (extracting EAR, MAR, Head Pose, and Gaze), and rule-based Temporal Analysis.
* **Phase 2 – Architecture Design & Proposal Finalization (Week 9 | Nov 16, 2026 – Nov 20, 2026):**
  * Finalize the scope of **Driver Drowsiness & Distraction Detection** around the Edge AI + AWS Serverless model.
  * Complete the 10-step architecture diagram, design authentication/data flows, and estimate operational costs via AWS Pricing Calculator.
* **Phase 3 – AWS Cloud Deployment, Edge Refinement & Testing (Week 10 | Nov 23, 2026 – Nov 27, 2026):**
  * Deploy the full AWS Serverless stack: DynamoDB, Cognito, Lambda (Writer/Reader), API Gateway, S3 (private), CloudFront (OAC), CloudWatch, IAM, CloudTrail, and AWS Budgets.
  * Implement the **Local Event Buffer & Retry** mechanism, fine-tune **Temporal Analysis**, and evaluate the stability of **Gaze Direction**.
  * Test detection accuracy across different lighting environments and camera angles, and validate offline-to-online data synchronization.
* **Phase 4 – Documentation & Final Project Demo (Week 11 | Nov 30, 2026):**
  * Finalize project documentation on the Hugo worklog site (GitHub Pages), conduct a live end-to-end demo from Edge to Cloud, and clean up AWS resources upon completion.

---

### 6. Budget & Cost Estimation

The system leverages an **AWS Serverless** architecture following a **Pay-as-you-go** pricing model to minimize operational expenses during development and low-traffic testing, paired with **AWS Budgets** for proactive spend monitoring and alerts.

| Component / Service | Estimated Scale / Configuration | Pricing Model & Cost Optimization |
| --- | --- | --- |
| **Edge Device (Webcam & Host Machine)** | Local AI inference via OpenCV + MediaPipe | Utilizes existing local hardware; eliminates cloud GPU/EC2 video processing costs. |
| **Amazon API Gateway (HTTP API)** | Ingests event metadata payloads and serves Dashboard queries | Uses HTTP API (more cost-effective than REST API), billed per actual request count. |
| **AWS Lambda** | 2 functions (`Event Writer` & `Event Reader`) with lightweight memory | Billed per invocation and execution duration (ms); covered largely by the AWS Free Tier. |
| **Amazon DynamoDB** | 1 table storing compact event metadata records | On-Demand capacity / Free Tier, scaling read/write costs strictly with actual traffic. |
| **Amazon Cognito** | Handles sign-up, sign-in, and JWT issuance for Dashboard users | Free for low Monthly Active Users (MAU) under Cognito's free tier allowance. |
| **Amazon S3 & CloudFront** | Hosts private static Dashboard assets and serves via CDN | Minimal static file footprint results in negligible storage and data transfer charges. |
| **CloudWatch, CloudTrail, IAM & Budgets** | Basic log retention, access governance, and budget alerts | IAM is free; configured with concise CloudWatch log retention and early AWS Budgets alerts. |

---

### 7. Risks & Mitigation Strategies

| Potential Risk | Impact | Likelihood | Mitigation & Recovery Strategy |
| --- | --- | --- | --- |
| **Loss or instability of internet connectivity in vehicles** | High | Medium | Decouple real-time AI inference onto the Edge Device so local alerts operate offline. Implement a **Local Event Buffer** with an automatic **Retry** loop to sync queued events once connectivity returns. |
| **Duplicate event records during Retry transmissions** | Medium | Medium | Assign a unique `event_id` to every detected event at the Edge and enforce a **Conditional `PutItem`** check in Amazon DynamoDB within the Lambda Event Writer to reject duplicate writes. |
| **Detection inaccuracy under poor lighting or varied camera angles** | High | Medium | Combine multiple behavioral signals (EAR, MAR, Head Pose) through **Temporal Analysis** rather than single-frame thresholds; test across diverse lighting/angle conditions and isolate **Gaze Direction** as an experimental feature prior to full adoption. |
| **Video privacy exposure and unauthorized Cloud access** | High | Low | Never transmit raw video to the cloud (metadata only); enforce least-privilege access via **IAM**, authenticate users with **Cognito JWT**, and block direct bucket access using **CloudFront OAC**. |
| **Unexpected AWS Cloud cost overruns** | Medium | Low | Adopt a pure Serverless pay-per-use architecture, configure automated spending thresholds via **AWS Budgets**, and regularly audit usage in **CloudWatch / Cost Explorer**. |
