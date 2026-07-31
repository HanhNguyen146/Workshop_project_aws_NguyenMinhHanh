---
title: "Event 2"
date: 2026-06-13
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Reflection on “DevOps Reality & URL Shortener Architecture”

### Purpose of the Event
- Discover the real work of DevOps and Data Analytics engineers.
- Learn how to design highly scalable systems on AWS.
- Understand personal development roadmaps and culture at multinational corporations (MNCs).

### List of Speakers
- Mr. Trong H. Truong
- Mr. Dinh Trung Kien & Nguyen Minh Tho
- Mr. Danh Hoang Hieu Nghi
- Mr. Dat Pham & Cuong Nguyen

---

### Key Highlights

Based on the provided materials, the meetup's content was divided into 4 main sharing sessions with the following topics and details:

**1. Topic: The Reality of a DevOps Engineer's Job (Trong H. Truong)**
The presentation focused on clarifying the real work of a DevOps engineer compared to common misconceptions:
*   **Current State and Demand:** The recruitment demand and salary of DevOps engineers in Vietnam (2016-2026) are showing an attractive growth trend.
*   **Myth vs Reality:** People often think DevOps is just about writing CI/CD pipelines, working with Docker/Kubernetes, or being the one deploying code and fixing system errors in the middle of the night. However, the actual work heavily depends on the context (company size, project, product complexity). Real tasks include: on-call duty, troubleshooting, debugging, access support, and investigating resource costs. "With great power comes great responsibility and headaches."
*   **Learning Path:** Beginners should start with foundational knowledge like Linux, Networking, programming languages (Python, Golang), Git, CI/CD, and Containers. Most importantly, understand how applications run, know how to build, test, deploy, and monitor small projects.
*   **Mindset of a Great DevOps:** Tools may change, but the foundation always remains. Be curious, learn continuously, have systems thinking, automate boring tasks, and communicate well.

**2. Topic: Building a Scalable URL Shortener Service on AWS (Dinh Trung Kien & Nguyen Minh Tho)**
The presentation dived deep into system architecture on the AWS platform:
*   **Basic vs Practical Model:** A basic URL shortening flow (User -> Frontend -> Backend -> Database) has the advantage of being easy to deploy and cheap, but has a fatal flaw of being vulnerable, high latency, having a Single Point of Failure, and being hard to scale.
*   **Detailed System Architecture:**
    *   **Frontend:** Using Amazon CloudFront, AWS WAF (security), and Amazon Amplify.
    *   **Key Generation Service (KGS):** Using Amazon ECS to run containers generating short codes and pushing them into a queue in Amazon ElastiCache (Redis).
    *   **Backend (URL Creation Flow):** Fetches short codes from Redis, associates them with long URLs via SpringBoot, and stores them in DynamoDB.
    *   **Backend (Access Flow):** The system prioritizes searching in the cache (Redis). Only if it's not there (cache miss) does it query the DynamoDB database.
*   **Core Lessons:** Separation of concerns (read and write), defense at the edge, prioritize Pre-computation over on-demand computation, and use the Cache-aside pattern to reduce the load on the Database.

**3. Topic: From First Cloud AI Journey to AWS Partner (Danh Hoang Hieu Nghi)**
Sharing about the 8-step career development journey in the AWS community:
*   **The 8-step Journey:** Starting from student curiosity -> Joining First Cloud Journey -> Learning from the community & Workshops -> Hands-on Labs -> Applying to school projects -> Building a Portfolio -> Becoming an AWS Partner -> Sharing back to the community (Share-Back).
*   **Support Programs:** Introduced the First Cloud AI Journey Program (where to learn foundational AWS knowledge like IAM, VPC, EC2, cost management...), AWS Student Builder Group (with benefits like badges, certificates, swag), and the AWS Community Builder program.

**4. Topic: Real Stories and Culture at Multinational Corporations - MNCs (Dat Pham & Cuong Nguyen)**
This section was divided into 2 main topics:

*   **Section 1: The Reality of a Data Analytics Engineer & Student Mindset**
    *   **Reality of Work:** Varies by industry. For example, at Kamereo, engineers focus on building performance reports, tracking GMV Dashboards, Fulfillment, Last Mile Cost, and Fill rate. At Colgate-Palmolive, the work leans more towards machine IoT data to optimize manufacturing and digital transformation.
    *   **Necessary Skills:** Critical thinking, communication skills, problem-solving, and especially the ability to "tell stories with data" (turning dry metrics into action-driving stories).
    *   **5-Stage Career Development Model:** (1) Follower, (2) Learner, (3) Problem Solver, (4) System Thinker, (5) Super Star.
*   **Section 2: Culture at Multinational Corporations (MNCs)**
    *   **Standard Recruitment Process:** Consists of 4 steps: Resume Screening (ATS) -> Competency Test (Logic, algorithms) -> Technical Interview (with Tech Lead/Manager applying the STAR model) -> Cultural Fit Assessment (with Leadership).
    *   **Corporate Culture:** Defined as "how individuals think, live, and act." For instance, multinational tech companies favor a "No-Blame Post-Mortem" culture (finding systemic root causes instead of blaming individuals), while FMCGs favor a "Caring & Inclusive" culture.
    *   **Global Standards & Career Philosophy:** Shifting from "Getting it done" to "Doing it right by standard" (like shifting from physical GMP/GDP standards to digital ISO 27001/SOC 2 standards). The sharing ended with the "Right Work" philosophy (Being a human - Doing a profession - Being a citizen) and emphasized the new generation's mission to shoulder the nation's digital lifeline.

---

### Results Achieved
- Better understand the reality of Cloud/DevOps jobs.
- Master the principles of designing high-load systems and cache-aside patterns.

---

### Applications to Work
- Apply static/dynamic processing separation architecture in school projects.
- Practice Root Cause Analysis skills.

---

### Experience in the Event
- The event provided very authentic perspectives, helping me avoid "illusions" about the IT industry's glamour.

#### Images from the Event
<div style="display: flex; gap: 20px;">
  <img src="/images/4-Events/event2/13_6_1.jpg" alt="Sự kiện" style="width: 50%; height: 300px; object-fit: cover;">
  <img src="/images/4-Events/event2/13_6_2.jpg" alt="Sự kiện" style="width: 50%; height: 300px; object-fit: cover;">
</div>
