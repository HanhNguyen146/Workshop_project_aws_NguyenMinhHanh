---
title: "Event 2"
date: 2026-06-13
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Bài thu hoạch “Thực tế DevOps & Kiến trúc URL Shortener”

### Mục Đích Của Sự Kiện
- Khám phá công việc thực sự của kỹ sư DevOps và dữ liệu (Data Analytics).
- Học hỏi cách thiết kế hệ thống có khả năng mở rộng lớn trên AWS.
- Tìm hiểu lộ trình phát triển bản thân và văn hóa tại tập đoàn đa quốc gia (MNC).

### Danh Sách Diễn Giả
- Anh Trọng H. Trương
- Anh Đinh Trung Kiên & Nguyễn Minh Thọ
- Anh Danh Hoàng Hiếu Nghị
- Anh Đạt Phạm & Cường Nguyễn

---

### Nội Dung Nổi Bật

Dựa vào các tài liệu bạn đã cung cấp, nội dung của buổi meetup được chia thành 4 phần chia sẻ chính với các chủ đề và chi tiết như sau:

**1. Chủ đề: Thực tế công việc của một DevOps Engineer (Trọng H. Trương)**
Bài trình bày tập trung vào việc làm rõ công việc thực sự của một kỹ sư DevOps so với những gì mọi người thường nghĩ:
*   **Thực trạng và Nhu cầu:** Nhu cầu tuyển dụng và mức lương của kỹ sư DevOps tại Việt Nam (2016-2026) đang có xu hướng tăng trưởng hấp dẫn.
*   **Lầm tưởng vs Thực tế:** Mọi người thường nghĩ DevOps chỉ là viết CI/CD pipelines, làm việc với Docker/Kubernetes, hay là người triển khai code và sửa lỗi hệ thống lúc nửa đêm. Tuy nhiên, thực tế công việc phụ thuộc rất nhiều vào ngữ cảnh (quy mô công ty, dự án, độ phức tạp của sản phẩm). Công việc thực sự bao gồm: trực hệ thống (on-call), xử lý sự cố, gỡ lỗi (troubleshooting), hỗ trợ quyền truy cập, và điều tra chi phí tài nguyên. "Quyền lực càng lớn, trách nhiệm và đau đầu càng nhiều".
*   **Lộ trình học tập:** Người mới nên bắt đầu từ các kiến thức nền tảng như Linux, Mạng (Networking), ngôn ngữ lập trình (Python, Golang), Git, CI/CD, và Containers. Quan trọng nhất là hiểu cách ứng dụng chạy, biết cách xây dựng, kiểm thử, triển khai và giám sát các dự án nhỏ.
*   **Tư duy của DevOps giỏi:** Công cụ có thể thay đổi nhưng nền tảng thì luôn giữ nguyên. Cần tò mò, học hỏi liên tục, tư duy hệ thống, tự động hóa các công việc nhàm chán và giao tiếp tốt. 

**2. Chủ đề: Xây dựng dịch vụ rút gọn URL có khả năng mở rộng trên AWS (Đinh Trung Kiên & Nguyễn Minh Thọ)**
Bài trình bày đi sâu vào kiến trúc hệ thống (Architecture) trên nền tảng AWS:
*   **Mô hình cơ bản vs Thực tế:** Một luồng rút gọn URL cơ bản (Người dùng -> Frontend -> Backend -> Database) có ưu điểm là dễ triển khai và rẻ, nhưng lại có nhược điểm chí mạng là dễ tổn thương, độ trễ cao, có điểm chết cục bộ (Single Point of Failure) và khó mở rộng.
*   **Kiến trúc hệ thống chi tiết:**
    *   **Frontend:** Sử dụng Amazon CloudFront, AWS WAF (bảo mật) và Amazon Amplify.
    *   **Key Generation Service (KGS):** Sử dụng Amazon ECS để chạy các container tạo sẵn mã ngắn (short codes) và đẩy (push) vào hàng đợi trong Amazon ElastiCache (Redis).
    *   **Backend (Luồng tạo URL):** Lấy mã ngắn từ Redis, liên kết với URL dài thông qua SpringBoot và lưu trữ vào DynamoDB.
    *   **Backend (Luồng truy cập):** Hệ thống ưu tiên tìm kiếm trong bộ nhớ đệm (Redis). Nếu không có (cache miss) mới truy vấn xuống cơ sở dữ liệu DynamoDB.
*   **Bài học cốt lõi:** Tách biệt các mối quan tâm (đọc và ghi), phòng thủ bảo mật ngay từ biên (Edge), ưu tiên tính toán trước (Pre-computation) thay vì tính toán theo yêu cầu, và sử dụng mô hình Cache-aside để giảm tải cho Database.

**3. Chủ đề: Từ First Cloud AI Journey đến AWS Partner (Danh Hoàng Hiếu Nghị)**
Chia sẻ về hành trình 8 bước phát triển sự nghiệp trong cộng đồng AWS:
*   **Hành trình 8 bước:** Bắt đầu từ sự tò mò của sinh viên -> Tham gia First Cloud Journey -> Học từ cộng đồng & Workshop -> Thực hành (Hands-on Labs) -> Ứng dụng vào dự án trường -> Xây dựng Portfolio -> Trở thành AWS Partner -> Chia sẻ lại cho cộng đồng (Share-Back).
*   **Các chương trình hỗ trợ:** Giới thiệu về First Cloud AI Journey Program (nơi học kiến thức nền tảng AWS như IAM, VPC, EC2, quản lý chi phí...), AWS Student Builder Group (với các quyền lợi như huy hiệu, chứng nhận, quà tặng swag), và chương trình AWS Community Builder.

**4. Chủ đề: Câu chuyện thực tế và Văn hóa tại Tập đoàn Đa quốc gia - MNC (Đạt Phạm & Cường Nguyễn)**
Phần này được chia làm 2 nội dung lớn:

*   **Section 1: Thực tế công việc của Data Analytics Engineer & Tư duy sinh viên**
    *   **Thực tế công việc:** Thay đổi tùy theo ngành nghề. Ví dụ tại Kamereo, kỹ sư tập trung xây dựng báo cáo hiệu suất, Dashboard theo dõi GMV, Fulfillment, chi phí vận chuyển (Last Mile Cost), và tỷ lệ lấp đầy đơn hàng (Fill rate). Tại Colgate-Palmolive, công việc lại thiên về dữ liệu IoT của máy móc để tối ưu sản xuất và chuyển đổi số.
    *   **Kỹ năng cần thiết:** Tư duy phản biện, kỹ năng giao tiếp, giải quyết vấn đề và đặc biệt là khả năng "kể chuyện với dữ liệu" (biến số liệu khô khan thành câu chuyện thúc đẩy hành động).
    *   **Mô hình phát triển nghề nghiệp 5 giai đoạn:** (1) Follower (Người thực thi), (2) Learner (Người học chủ động), (3) Problem Solver (Người giải quyết vấn đề), (4) System Thinker (Người tư duy hệ thống - nhìn bức tranh toàn cảnh), (5) Super Star (Người dẫn dắt thế hệ kế cận).
*   **Section 2: Văn hóa tại Tập đoàn Đa quốc gia (MNCs)**
    *   **Quy trình tuyển dụng chuẩn:** Gồm 4 bước: Sàng lọc hồ sơ (ATS/Sơ vấn) -> Test năng lực (Logic, thuật toán) -> Phỏng vấn chuyên môn (với Tech Lead/Manager áp dụng mô hình STAR) -> Đánh giá mức độ hòa hợp văn hóa (với Leadership).
    *   **Văn hóa doanh nghiệp:** Được định nghĩa là "cách nghĩ, cách sống, cách làm của từng con người". Ví dụ: Các công ty công nghệ đa quốc gia chuộng văn hóa "No-Blame Post-Mortem" (tìm gốc rễ hệ thống thay vì đổ lỗi cá nhân), trong khi FMCG chuộng văn hóa "Caring & Inclusive".
    *   **Tiêu chuẩn toàn cầu & Triết lý nghề nghiệp:** Chuyển dịch từ việc "Làm được" sang "Làm đúng chuẩn" (như chuyển từ tiêu chuẩn vật lý GMP/GDP sang tiêu chuẩn số ISO 27001/SOC 2). Bài chia sẻ kết thúc bằng triết lý "Đúng việc" (Làm người - Làm nghề - Làm dân) và nhấn mạnh sứ mệnh của thế hệ mới là gánh vác huyết mạch số của quốc gia.

---

### Kết quả đạt được
- Hiểu rõ hơn về thực tế công việc ngành Cloud/DevOps.
- Nắm vững nguyên lý thiết kế hệ thống chịu tải cao và cache-aside.

---

### Ứng Dụng Vào Công Việc
- Áp dụng kiến trúc tách biệt xử lý tĩnh/động vào dự án môn học.
- Rèn luyện kỹ năng phân tích lỗi (Root Cause Analysis).

---

### Trải nghiệm trong event
- Sự kiện đem lại những góc nhìn rất chân thực, giúp em tránh bị "ảo tưởng" về những hào quang của ngành IT.

#### Một số hình ảnh khi tham gia sự kiện
<div style="display: flex; gap: 20px;">
  <img src="/images/4-Events/event2/13_6_1.jpg" alt="Sự kiện" style="width: 50%; height: 300px; object-fit: cover;">
  <img src="/images/4-Events/event2/13_6_2.jpg" alt="Sự kiện" style="width: 50%; height: 300px; object-fit: cover;">
</div>
