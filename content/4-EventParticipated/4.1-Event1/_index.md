---
title: "Event 1"
date: 2026-06-06
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Reflection on “AWS Community Meetup”

### Purpose of the Event

- Learn about technologies like AWS WAF, ML NIDS, Docker and their practical applications.
- Listen to career stories from IT Helpdesk to Sysadmin, and the art of teamwork.
- Explore new trends like GraphRAG and Multiplayer games on AWS.

### List of Speakers

- Mr. Le Hoang Gia Dai
- Mr. Bao Huynh
- Mr. Tran Trung Vinh
- Mr. Nguyen Quoc Bao
- Mr. Truong Huy Phuoc
- Mr. Viet Phat

---

### Key Highlights

Below is the detailed content of the 6 presentations at the event, compiled from the provided materials:

**1. "AWS WAF & ML NIDS" - Le Hoang Gia Dai**
*   **Topic:** Applying Machine Learning to build a Network Intrusion Detection System (NIDS) on AWS, combined with Web Application Firewall (WAF) to detect cyber attacks.
*   **Detailed Content:**
    *   **WAF Limitations:** AWS WAF protects well at the HTTP/HTTPS layer and defends against common attacks using rule-based sets. However, WAF struggles with unprecedented (zero-day) attacks or novel abnormal behaviors.
    *   **ML NIDS Solution:** NIDS helps monitor network traffic and detect abnormal behaviors. By applying Machine Learning, the system can automatically analyze massive data, learn from actual networks, and adapt quickly to new types of attacks.
    *   **Practical Implementation:** The speaker used the CSE-CIC-IDS2018 dataset (cleaned, error data removed, labels balanced) to train ML models (LightGBM, Random Forest, XGBoost).
    *   **AWS Architecture:** The system connects AWS WAF, EC2, ALB, Kinesis, Lambda, and integrates with a Dashboard for real-time attack monitoring.
    *   **Lessons & Future:** Data quality determines Machine Learning performance. The future development direction is integrating GenAI via Amazon Bedrock and automating response actions.

**2. "Docker" - Bao Huynh**
*   **Topic:** Introduction to Docker and Containerization technology.
*   **Detailed Content:**
    *   **Virtual Machines (VMs) vs Containers:** Virtual Machines are quite heavy, require a lot of memory, and run separate Operating Systems (OS). Conversely, Containers share the OS with the host machine, are ultra-lightweight, save resources, and can boot in milliseconds.
    *   **What is Docker:** This is a platform for packaging applications along with all libraries and related configurations into a single package (container). Docker's philosophy is "build once, run anywhere" (package once, run everywhere without worrying about compatibility issues).
    *   **Core Components:** 
        *   *Docker Images:* Template files (created by Dockerfile scripts divided into multiple layers). 
        *   *Docker Containers:* The actual running instances of applications isolated on the machine.
    *   **Basic Commands & Applications:** Introduced command groups for managing images, containers, networks, volumes, and Docker applications in CI/CD pipelines, Microservices architecture, testing environments, and migrating legacy applications to the Cloud.

**3. "From IT Helpdesk to Senior Sysadmin" - Tran Trung Vinh**
*   **Topic:** The real career journey from an IT Helpdesk role to a Senior Sysadmin, along with the transition path to Cloud and DevOps culture.
*   **Detailed Content:**
    *   **Starting from Helpdesk:** The initial job equipped him with communication and troubleshooting skills. The turning point came when the speaker decided to deeply study Linux, Networking, and build home practice labs.
    *   **Sysadmin Job:** Revolves around server administration, network infrastructure, security patching, and resource planning. The core lessons are: automate repetitive tasks, document configurations, monitor the system before issues occur, and "absolutely never test directly on the production environment".
    *   **Cloud & DevOps Roadmap (First Cloud Journey):** Moving from traditional physical server thinking (On-Premise) to Cloud thinking (Pay-as-you-go, AWS). Next is applying Infrastructure as Code (Terraform) and finally DevOps culture (CI/CD, Docker).
    *   **Career Advice:** In interviews, real projects are more important than certificates. Advises young people not to learn too many things at once, dive deep into 1-2 core skills first, and don't be afraid of failure.

**4. "Connecting Godot Clients with AWS WebSockets" - Nguyen Quoc Bao**
*   **Topic:** Designing a Cloud Multiplayer feature by connecting the Godot 4 game engine with AWS WebSockets.
*   **Detailed Content:**
    *   **Network Architecture Comparison:** FPS or racing games often use the UDP protocol due to very low latency. Meanwhile, WebSockets are suitable for turn-based games thanks to stable two-way communication despite higher latency. HTTP Polling is too slow for gaming.
    *   **AWS Architecture:** The Godot game client connects to **API Gateway WebSocket**, then sends routes ($connect, $disconnect, $default) to the **AWS Lambda** function to process logic, while storing player states and matchmaking in the **DynamoDB** database.
    *   **Programming on Godot Client:** Uses `WebSocketPeer` to open a connection. The `poll()` function is called continuously every frame to check messages. The game uses a JSON format file to send matchmaking signals (`finding_match`) or in-game choices (`choice`).
    *   **Challenges:** The operational process encounters some disadvantages like: virtual/dead connections, high DynamoDB scanning costs, and the "Stateless" nature of Lambda. For games needing fast speed and continuous synchronization, AWS GameLift (Dedicated Server) will be an optimal solution in the future.

**5. "The Art of Effective Teamwork" - Truong Huy Phuoc**
*   **Topic:** The art of effective teamwork.
*   **Detailed Content:**
    *   **4 Golden Rules:** 
        1) Set clear and common goals for the whole group. 
        2) Assign the right person to the right position. 
        3) Communicate openly and practice Active Listening. 
        4) Uphold the responsibility of each individual.
    *   **Digital Tools:** Introduced platforms supporting project management and online communication including Trello, ClickUp, Google Workspace, Slack, and Discord.

**6. "Build GraphRAG applications" - Viet Phat**
*   **Topic:** Building GraphRAG applications using Amazon Bedrock and Amazon Neptune.
*   **Detailed Content:**
    *   **What is RAG & Limitations:** RAG helps provide external knowledge to Large Language Models (LLMs). However, traditional RAG struggles with multi-hop reasoning, such as when synthesizing cross-relationships between multiple different documents/entities.
    *   **GraphRAG Solution:** Transforming data into a Knowledge Graph with Nodes (entities) and Edges (relationships). From there, the system can traverse multiple connection points (graph traversal) to find accurate answers to complex questions.
    *   **Managed Route Architecture:** Using AWS's fully managed tool, Amazon Bedrock Knowledge Bases, to chunk data and create embeddings, combined with Amazon Neptune Analytics acting as the graph storage brain and discovering connections.
    *   **Custom Route Architecture:** Self-processing the pipeline using the LLamaindex library (to prepare data, build graph structure) and using Amazon Neptune to store KG, leveraging Cypher querying capabilities and traversing multiple nodes.

---

### Results Achieved

- Grasp the latest technology trends in security, containers, and AI.
- Consolidate personal career development orientation.

---

### Applications to Work

- Apply Docker in personal projects for easy deployment.
- Apply the 4 golden rules in teamwork.

---

### Experience in the Event

- Experience an open networking atmosphere, listening to authentic career stories from predecessors.

#### Images from the Event

<div style="display: flex; gap: 20px;">
  <img src="/images/4-Events/event1/6_6_1.jpg" alt="Sự kiện" style="width: 50%; height: 300px; object-fit: cover;">
  <img src="/images/4-Events/event1/6_6_2.jpg" alt="Sự kiện" style="width: 50%; height: 300px; object-fit: cover;">
  <img src="/images/4-Events/event1/6_6_3.jpg" alt="Sự kiện" style="width: 50%; height: 300px; object-fit: cover;">
</div>
