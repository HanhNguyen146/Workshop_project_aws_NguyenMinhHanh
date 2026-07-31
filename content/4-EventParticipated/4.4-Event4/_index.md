---
title: "Event 4"
date: 2026-07-25
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

# Reflection on “Agentic AI Build Week & Hackathon Journey”

### Purpose of the Event

- Experience a continuous 24-hour cycle of ideating and perfecting Agentic AI products.
- Listen to outstanding practical AI solutions from competing teams.
- Develop resilience to overcome technical issues and manage time.

### List of Speakers

- Mr. Joseph Marazota (Head of Technology for ASEAN, AWS)
- Hackathon Teams (One Team, Signal Scout, Team Plan, 3K, Six Pillar)

---

### Key Highlights

Below are the details of each sharing session from speakers and competing teams at the Agentic AI Build Week Hackathon event:

**1. Opening Remarks by Mr. Joseph Marazota (Head of Technology for Asian, AWS)**
*   **Technology Journey:** He shared about his career 20 years ago, comparing it with the luck of today's youth being invested in by AWS and having the opportunity to access new technologies. While releasing a product previously took several months, AI agents can now do it every minute.
*   **AI Vision:** Artificial Intelligence is transforming every industry (retail, financial services, etc.). However, humans are still the deciding factor (human in the loop) to control and give directions to robots or AI agents. He advised young people to boldly challenge old limits and maintain a lifelong learning spirit.

**2. One Team (First Prize) - KFC Food Ordering AI Agent Project**
*   **Problem:** Ordering food via an app creates many barriers (having to download the app, log in, enter card details), plus the lesson from McDonald's AI system suffering from "hallucinations" leading to incorrect orders.
*   **Solution:** Created an omni-channel AI ordering chatbot (focusing on Zalo), helping customers order directly through natural conversation without switching apps.
*   **Technology & Cost:** The team used Tiny Fish to scrape data from the KFC website, used **Agent Core** so the system has memory (remembering the customer's order history). The system has a latency of only 3-5 seconds and extremely low cost, about $0.006 USD per order.

**3. Signal Scout Team (Second Prize) - Business Strategy Analysis Project**
*   **Problem:** Instead of focusing on mainstream technology, the team wanted to solve a real business problem of collecting scattered business signals from rival companies (financial reports, shareholder talks).
*   **Solution:** Built a system to gather competitor information, connect them to forecast Return on Investment (ROI) and risks if the user's company applied a similar strategy.
*   **Technology:** Architecture ran on AWS with Amplify, Cognito. Used Agent Core to coordinate Subagents. Used Tiny Fish and Apify to collect web data, then Bedrock Guardrail and LlamaIndex to score and analyze data to prevent AI hallucination.

**4. Team Plan - AI Assistant for Solution Architect (SA) Project**
*   **Problem:** Solution Architects (SA) are often under pressure when customers urgently request a system architecture diagram and cost breakdown within 1-2 days, sometimes even overnight.
*   **Solution:** Built an application receiving natural language requests from users. The AI will automatically analyze, draw architecture diagrams on Draw.io, calculate costs, and output code snippets (Terraform/CloudFormation) to automatically deploy infrastructure.
*   **Technology:** Strictly controlled workflow and context. The system will block unauthorized services (black list) right from the output to ensure the AI strictly complies with the enterprise's internal templates.

**5. 3K Team - Sheper (Crowd Flow Management) Project**
*   **Problem:** Human congestion at airports, supermarkets, or event venues.
*   **Solution:** Built an AI-integrated surveillance camera system to automatically track, detect areas that are or will be congested, and dispatch support personnel.
*   **Technology:** Used Kinesis Video Stream, Fargate. Integrated YOLO model to recognize people and ByteTrack to attach IDs for object tracking. Data was sent to an Agent connected to Amazon Bedrock for the AI to compute and suggest solutions.
*   **Experience:** The team shared memories of staying up all night, rookie mistakes like accidentally pushing the .env file to GitHub, and emphasized the importance of controlling a "just right" project scope in Hackathons.

**6. Six Pillar Team - Adaptive Workflow Engine (Anti-Money Laundering) Project**
*   **Problem:** Traditional anti-money laundering systems generate 90-95% false alerts, making data analysts spend hours exhaustively reviewing them manually.
*   **Solution:** Built an AI system to assist in investigating financial transactions by automatically checking profiles (KYC), cash flows, cross-referencing laws, and generating evidence reports.
*   **Technology:** A 3-layer architecture. Layer 1 uses Machine Learning models (XGBoost), Kinesis, and Lambda for quick transaction filtering. Layer 2 uses Step Functions to call Agents to retrieve in-depth info. Layer 3 is an interface for humans to make final decisions. The system integrates enterprise-grade security with KMS, Security Hub, and X-Ray for tracing and data protection.

---

### Results Achieved

- Mastered how to combine Agentic AI models with AWS cloud infrastructure.
- Understood the "Done is better than perfect" philosophy in Hackathons.

---

### Applications to Work

- Apply Agentic AI in personal projects to automate action chains.
- Better manage project scope in future teamwork.

---

### Experience in the Event

- Exploded with emotions, debugging overnight until morning and bursting with joy upon successful demo.

#### Images from the Event

<div style="display: flex; gap: 20px; flex-wrap: wrap; justify-content: center;">
  <img src="/images/4-Events/4.3-hackathon-sharing/hackathon1.jpg" style="width: 45%; height: 250px; object-fit: cover;">
  <img src="/images/4-Events/4.3-hackathon-sharing/hackathon2.jpg" style="width: 45%; height: 250px; object-fit: cover;">
  <img src="/images/4-Events/4.3-hackathon-sharing/hackathon3.jpg" style="width: 45%; height: 250px; object-fit: cover;">
  <img src="/images/4-Events/4.3-hackathon-sharing/hackathon4.jpg" style="width: 45%; height: 250px; object-fit: cover;">
  <img src="/images/4-Events/4.3-hackathon-sharing/hackathon5.jpg" style="width: 45%; height: 250px; object-fit: cover;">
</div>
