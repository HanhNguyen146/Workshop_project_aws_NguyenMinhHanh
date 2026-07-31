---
title: "Event 3"
date: 2026-07-11
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Reflection on “AWS Security, Monitoring & Certifications”

### Purpose of the Event

- Explore the roadmap for the AWS Cloud Practitioner certification.
- Discover AI-automated security penetration testing solutions.
- Understand the importance of Monitoring systems and SLA for user experience.

### List of Speakers

- Mr. Ngo Le Tan Huy
- Mr. Thinh Nguyen
- Mr. Nguyen Huynh Son

---

### Key Highlights

Based on the materials provided, below is a detailed breakdown of the 3 sharing sessions:

**Session 1: Roadmap to Conquering the AWS Cloud Practitioner Certification**
*   **Speaker:** Ngo Le Tan Huy.
*   **Exam Overview:** This is a foundational certification focusing on the big picture without requiring candidates to know how to code or configure systems deeply. The exam consists of 65 multiple-choice questions, lasts 90 minutes (non-native English speakers get an extra 30 minutes), with a passing score of 700/1000 and is valid for 3 years.
*   **Exam Structure (4 Domains):**
    *   *Domain 1 - Cloud Concepts (24%):* Does not dive into technicalities but focuses on digital transformation mindset, the 6 benefits of AWS Cloud, AWS Well-Architected Framework (WAF), AWS Cloud Adoption Framework (CAF), and the Shared Responsibility Model.
    *   *Domain 2 - Security and Compliance (30%):* Identity and Access Management (IAM) with the principle of least privilege, differences between Security Groups and NACLs, DDoS protection services (AWS Shield, WAF), and compliance reports (AWS Artifact).
    *   *Domain 3 - Cloud Technology and Services (34%):* Knowledge of global infrastructure (Region, AZ, Edge), compute services (EC2, Lambda), storage/databases (S3, EBS, RDS, DynamoDB...), and networking (VPC, Route 53).
    *   *Domain 4 - Billing, Pricing, and Support (12%):* EC2 pricing models (On-Demand, Spot...), cost management tools (AWS Cost Explorer, Budgets), and AWS Support plans.
*   **Study & Exam Experience:** 
    *   *Studying:* Apply the "Map Keyword Thinking" method (associate each service with 1-2 practical keywords), focus on analyzing deeply why questions are wrong during mock tests, and practice directly on the AWS Free Tier.
    *   *Exam:* Use the process of elimination (often there are 2 completely made-up answers), Don't overthink, be careful with trap keywords in English like "Not", "Least cost", and use the "Flag for review" feature to mark uncertain questions.

**Session 2: Web Application Security with AWS Security Agent**
*   **Speaker:** Thinh Nguyen (Nguyen Tuan Thinh).
*   **Security Bottlenecks:** Manual penetration testing (pentest) currently takes a lot of time (weeks), is expensive ($5,000 - $20,000/time), and the coverage level depends on the skill or mood of the tester.
*   **Solution - Frontier Agent:** This is an autonomous agent powered by Amazon Bedrock, capable of planning and executing security without human intervention. The phases include:
    *   *Design Review:* Analyzes architecture documents before writing code to review compliance, free 200 times/month.
    *   *Code Security Review:* Integrates directly into GitHub/GitLab Pull Requests to scan for vulnerabilities and suggest code patches, free 1,000 times/month.
    *   *Automated Pentesting:* Practically attacks the running application using multi-step exploit chains and provides clear evidence.
*   **Cost:** After a 2-month free trial, the cost is $50/task hour. A real case study showed the total cost was about $1,500 - $2,500, considered a "bargain" compared to hiring a pentest team for $10,000.
*   **Limitations:** The system will be blocked by authentication layers (MFA, biometrics, mTLS), struggles to detect business logic vulnerabilities, and can burn task hours (money) very quickly with complex applications, so strict monitoring is required.

**Session 3: SLA and Monitoring**
*   **Speaker:** Nguyen Huynh Son.
*   **Role of SLA & Monitoring:** SLA (Service Level Agreement) helps shape expectations and manage risks. Monitoring is part of risk management to early detect issues before the SLA impact turns into customer complaints, operating in a loop: Identify -> Monitor -> Respond -> Improve.
*   **Monitoring Pyramid Model:** Top-down order: Customer Experience -> Business Metrics -> Application -> Infrastructure -> Cloud Provider. Monitoring hardware from the bottom up is not enough.
*   **The Monitoring Paradox:** "Healthy infrastructure does not equal happy user experience." 
    *   In a real demo example: Server metrics (CPU) might still be very green at 18% and Health check (App process check) reports "200 OK", but a Database connection error prevents users from logging in (successful login rate drops from 100% to 0%).
*   **Alerting Flow:** Monitoring information is only valuable if it alerts before customers complain. The basic flow is: Custom metric -> Set alarm threshold (CloudWatch Alarm) -> Distribution network (SNS Topic) -> Notification via Email / Slack.
*   **Core Lessons:** Infrastructure metrics cannot tell the whole story; you need to know exactly what the user is doing (logging in, purchasing...). AWS only commits to the SLA ensuring the cloud platform, while the system designer must take responsibility for the actual customer experience.

---

### Results Achieved

- Formulated a systematic AWS certification study plan.
- Understood the value of placing monitoring metrics in the right places.

---

### Applications to Work

- Configured basic CloudWatch for personal apps to receive early alerts.
- Started studying for the Cloud Practitioner certification.

---

### Experience in the Event

- Strongly impressed by AI's ability to act as a security expert to penetrate systems.

#### Images from the Event

<div style="display: flex; justify-content: center;">
  <img src="/images/4-Events/event3/11_7.jpg" alt="Sự kiện" style="width: 50%; height: 300px; object-fit: cover;">
  <img src="/images/4-Events/event3/3.png" alt="Sự kiện" style="width: 50%; height: 300px; object-fit: cover;">
</div>
