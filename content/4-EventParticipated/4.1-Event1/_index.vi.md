---
title: "Event 1"
date: 2026-06-06
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch “AWS Community Meetup”

### Mục Đích Của Sự Kiện

- Tìm hiểu về các công nghệ như AWS WAF, ML NIDS, Docker và cách ứng dụng vào thực tế.
- Lắng nghe những câu chuyện nghề nghiệp từ IT Helpdesk đến Sysadmin, nghệ thuật làm việc nhóm.
- Khám phá các xu hướng mới như GraphRAG, Multiplayer game trên AWS.

### Danh Sách Diễn Giả

- Anh Lê Hoàng Gia Đại
- Anh Bảo Huỳnh
- Anh Trần Trung Vinh
- Anh Nguyễn Quốc Bảo
- Anh Trương Huy Phước
- Anh Việt Phát

---

### Nội Dung Nổi Bật

Dưới đây là chi tiết nội dung của 6 bài trình bày trong sự kiện, được tổng hợp từ các tài liệu bạn đã cung cấp:

**1. "AWS WAF & ML NIDS" - Lê Hoàng Gia Đại**
*   **Chủ đề:** Ứng dụng Machine Learning để xây dựng Hệ thống phát hiện xâm nhập mạng (NIDS) trên AWS, kết hợp với Tường lửa ứng dụng web (WAF) để phát hiện tấn công mạng.
*   **Nội dung chi tiết:**
    *   **Giới hạn của WAF:** AWS WAF bảo vệ tốt ở lớp HTTP/HTTPS và chống lại các kiểu tấn công phổ biến bằng các bộ quy tắc (rule-based). Tuy nhiên, WAF gặp khó khăn khi đối mặt với các cuộc tấn công chưa từng xuất hiện (zero-day) hoặc các hành vi bất thường mới lạ.
    *   **Giải pháp ML NIDS:** NIDS giúp theo dõi lưu lượng mạng và phát hiện các hành vi bất thường. Bằng cách ứng dụng Machine Learning, hệ thống có khả năng tự động phân tích dữ liệu khổng lồ, học từ mạng thực tế và thích ứng nhanh với các kiểu tấn công mới.
    *   **Triển khai thực tế:** Diễn giả sử dụng tập dữ liệu CSE-CIC-IDS2018 (được làm sạch, loại bỏ dữ liệu lỗi, cân bằng nhãn) để huấn luyện mô hình ML (LightGBM, Random Forest, XGBoost).
    *   **Kiến trúc trên AWS:** Hệ thống kết nối AWS WAF, EC2, ALB, Kinesis, Lambda và tích hợp cùng một bảng điều khiển (Dashboard) giám sát tấn công theo thời gian thực.
    *   **Bài học & Tương lai:** Chất lượng dữ liệu quyết định hiệu năng của Machine Learning. Hướng phát triển sắp tới là tích hợp GenAI thông qua Amazon Bedrock và tự động hóa các hành động ứng phó.

**2. "Docker" - Bảo Huỳnh (Bao Huynh)**
*   **Chủ đề:** Giới thiệu tổng quan về Docker và công nghệ Containerization.
*   **Nội dung chi tiết:**
    *   **Ảo hóa (VMs) vs Container:** Máy ảo (Virtual Machines) khá nặng nề, cần bộ nhớ lớn và chạy hệ điều hành (OS) riêng biệt. Ngược lại, Container chia sẻ hệ điều hành với máy chủ gốc, siêu nhẹ, tiết kiệm tài nguyên và có thể khởi động chỉ trong phần nghìn giây.
    *   **Docker là gì:** Đây là nền tảng đóng gói ứng dụng cùng toàn bộ thư viện, cấu hình liên quan vào một kiện hàng duy nhất (container). Triết lý của Docker là "build once, run anywhere" (đóng gói một lần, chạy mọi nơi không lo lỗi tương thích).
    *   **Thành phần cơ bản:** 
        *   *Docker Images:* Các file bản mẫu (được tạo bởi các tập lệnh Dockerfile chia thành nhiều layer). 
        *   *Docker Containers:* Các phiên bản ứng dụng thực tế đang chạy tách biệt trên máy.
    *   **Lệnh cơ bản & Ứng dụng:** Giới thiệu các nhóm lệnh quản lý image, container, network, volume và ứng dụng Docker trong chuỗi CI/CD, kiến trúc Microservices, môi trường test cũng như chuyển đổi các ứng dụng cũ lên Cloud.

**3. "From IT Helpdesk to Senior Sysadmin" - Trần Trung Vinh (Tran Trung Vinh)**
*   **Chủ đề:** Hành trình sự nghiệp thực tế từ vai trò IT Helpdesk lên Senior Sysadmin, cùng lộ trình chuyển dịch sang Cloud và văn hóa DevOps.
*   **Nội dung chi tiết:**
    *   **Khởi đầu từ Helpdesk:** Công việc ban đầu trang bị kỹ năng giao tiếp và xử lý sự cố. Bước ngoặt đến khi diễn giả quyết định học sâu về Linux, Networking và tự xây dựng các phòng lab thực hành tại nhà.
    *   **Công việc của Sysadmin:** Xoay quanh quản trị máy chủ, hạ tầng mạng, bản vá bảo mật và lập kế hoạch tài nguyên. Bài học cốt lõi là: tự động hóa các tác vụ lặp lại, ghi chép lại cấu hình (document), theo dõi hệ thống trước khi sự cố xảy ra và "tuyệt đối không bao giờ test thẳng trên môi trường production".
    *   **Lộ trình Cloud & DevOps (First Cloud Journey):** Đi từ tư duy máy chủ vật lý truyền thống (On-Premise) sang tư duy Đám mây (Pay-as-you-go, AWS). Tiếp đến là áp dụng Infrastructure as Code (Terraform) và cuối cùng là văn hóa DevOps (CI/CD, Docker).
    *   **Lời khuyên nghề nghiệp:** Trong các cuộc phỏng vấn, dự án thực tế quan trọng hơn chứng chỉ. Khuyên các bạn trẻ không nên học quá nhiều thứ cùng lúc, hãy đi sâu vào 1-2 kỹ năng cốt lõi trước và đừng sợ gặp thất bại.

**4. "Connecting Godot Clients with AWS WebSockets" - Nguyễn Quốc Bảo (Nguyen Quoc Bao)**
*   **Chủ đề:** Thiết kế tính năng Multiplayer (nhiều người chơi) trên đám mây bằng cách kết nối game engine Godot 4 với AWS WebSockets.
*   **Nội dung chi tiết:**
    *   **So sánh kiến trúc mạng:** Các tựa game FPS hoặc đua xe thường dùng giao thức UDP vì độ trễ rất thấp. Trong khi đó, WebSocket phù hợp cho game đánh theo lượt (turn-based) nhờ giao tiếp 2 chiều ổn định dù độ trễ cao hơn. HTTP Polling thì quá chậm để làm game.
    *   **Kiến trúc AWS:** Game client Godot kết nối tới **API Gateway WebSocket**, sau đó gửi các route ($connect, $disconnect, $default) tới hàm **AWS Lambda** để xử lý logic, đồng thời lưu trạng thái người chơi, ghép trận tại cơ sở dữ liệu **DynamoDB**.
    *   **Lập trình trên Godot Client:** Sử dụng `WebSocketPeer` để mở kết nối. Hàm `poll()` được gọi liên tục mỗi khung hình để kiểm tra tin nhắn. Game dùng file định dạng JSON để gửi tín hiệu ghép trận (`finding_match`) hoặc các lựa chọn trong game (`choice`).
    *   **Thách thức:** Quá trình vận hành gặp một số bất lợi như: kết nối ảo/chết, chi phí quét dữ liệu DynamoDB tăng cao và tính chất "không lưu trạng thái" (Stateless) của Lambda. Với các game cần tốc độ nhanh và đồng bộ liên tục, AWS GameLift (Dedicated Server) sẽ là giải pháp tối ưu hơn trong tương lai.

**5. "The Art of Effective Teamwork" - Trương Huy Phước (Truong Huy Phuoc)**
*   **Chủ đề:** Nghệ thuật làm việc nhóm hiệu quả.
*   **Nội dung chi tiết:**
    *   **4 Nguyên tắc vàng:** 
        1) Đặt ra các mục tiêu rõ ràng và chung cho cả nhóm. 
        2) Phân công đúng người, đúng vị trí. 
        3) Giao tiếp cởi mở và chủ động lắng nghe (Active Listening). 
        4) Nêu cao tính trách nhiệm của mỗi cá nhân.
    *   **Công cụ làm việc số (Digital Tools):** Giới thiệu các nền tảng hỗ trợ quản lý dự án và giao tiếp trực tuyến bao gồm Trello, ClickUp, Google Workspace, Slack và Discord.

**6. "Build GraphRAG applications" - Việt Phát (Viet Phat)**
*   **Chủ đề:** Xây dựng ứng dụng GraphRAG sử dụng Amazon Bedrock và Amazon Neptune.
*   **Nội dung chi tiết:**
    *   **RAG là gì & Hạn chế:** RAG giúp cấp thêm kiến thức bên ngoài cho các mô hình ngôn ngữ lớn (LLM). Tuy nhiên, RAG truyền thống lại gặp khó khăn trong việc suy luận đa chặng (multi-hop reasoning), ví dụ như khi phải tổng hợp mối quan hệ vắt chéo giữa nhiều tài liệu/thực thể khác nhau.
    *   **Giải pháp GraphRAG:** Đưa dữ liệu thành một Đồ thị tri thức (Knowledge Graph) với các Nodes (thực thể) và Edges (mối quan hệ). Từ đó hệ thống có thể duyệt qua nhiều điểm nối (graph traversal) để tìm ra câu trả lời chính xác cho những câu hỏi phức tạp.
    *   **Kiến trúc Managed Route:** Dùng công cụ quản lý trọn gói của AWS là Amazon Bedrock Knowledge Bases để băm nhỏ dữ liệu và tạo embeddings, kết hợp với Amazon Neptune Analytics đóng vai trò bộ não lưu trữ đồ thị và khám phá các mối liên hệ.
    *   **Kiến trúc Custom Route:** Tự xử lý pipeline bằng thư viện LLamaindex (để chuẩn bị dữ liệu, xây dựng cấu trúc đồ thị) và sử dụng Amazon Neptune để lưu trữ KG, tận dụng khả năng truy vấn Cypher và đi qua nhiều node.

---

### Kết quả đạt được

- Nắm bắt được những xu hướng công nghệ mới nhất về bảo mật, container và AI.
- Củng cố định hướng phát triển sự nghiệp cá nhân.

---

### Ứng Dụng Vào Công Việc

- Vận dụng Docker vào các dự án cá nhân để dễ dàng triển khai.
- Áp dụng 4 nguyên tắc vàng trong quá trình làm việc nhóm.

---

### Trải nghiệm trong event

- Trải nghiệm không khí giao lưu cởi mở, lắng nghe những chia sẻ rất thật về nghề từ những người đi trước.

#### Một số hình ảnh khi tham gia sự kiện

<div style="display: flex; gap: 20px;">
  <img src="/images/4-Events/event1/6_6_1.jpg" alt="Sự kiện" style="width: 50%; height: 300px; object-fit: cover;">
  <img src="/images/4-Events/event1/6_6_2.jpg" alt="Sự kiện" style="width: 50%; height: 300px; object-fit: cover;">
  <img src="/images/4-Events/event1/6_6_3.jpg" alt="Sự kiện" style="width: 50%; height: 300px; object-fit: cover;">
</div>
