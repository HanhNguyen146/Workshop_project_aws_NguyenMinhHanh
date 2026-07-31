---
title: "Event 4"
date: 2026-07-25
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

# Bài thu hoạch “Agentic AI Build Week & Hackathon Journey”

### Mục Đích Của Sự Kiện
- Trải nghiệm chuỗi 24 giờ liên tục lên ý tưởng và hoàn thiện sản phẩm AI Agentic.
- Lắng nghe các giải pháp AI thực chiến xuất sắc từ các đội thi.
- Rèn luyện bản lĩnh vượt qua sự cố kỹ thuật và quản lý thời gian.

### Danh Sách Diễn Giả
- Ông Joseph Marazota (Head of Technology của Asian, AWS)
- Các đội thi Hackathon (One Team, Signal Scout, Team Plan, 3K, Six Pillar)

---

### Nội Dung Nổi Bật

Dưới đây là chi tiết nội dung từng phần chia sẻ của các diễn giả và các đội thi trong sự kiện Agentic AI Build Week Hackathon:

**1. Phát biểu khai mạc từ ông Joseph Marazota (Head of Technology của Asian, AWS)**
*   **Hành trình công nghệ:** Ông chia sẻ về sự nghiệp 20 năm trước của mình, so sánh với sự may mắn của giới trẻ hiện nay khi được AWS đầu tư và có cơ hội tiếp cận công nghệ mới. Nếu trước đây việc phát hành sản phẩm (release) mất vài tháng, thì nay các AI agent có thể thực hiện mỗi phút.
*   **Tầm nhìn về AI:** Trí tuệ nhân tạo đang chuyển đổi mọi ngành công nghiệp (bán lẻ, dịch vụ tài chính, v.v.). Tuy nhiên, con người vẫn là yếu tố quyết định (human in the loop) để kiểm soát và đưa ra định hướng cho các robot hay AI agent. Ông khuyên các bạn trẻ hãy mạnh dạn thách thức những giới hạn cũ và duy trì tinh thần học tập suốt đời.

**2. Đội One Team (Giải Nhất) - Dự án AI Agent đặt đồ ăn cho KFC**
*   **Vấn đề:** Việc đặt đồ ăn qua ứng dụng gây ra nhiều rào cản (phải tải app, đăng nhập, nhập thẻ) và bài học từ việc hệ thống AI của McDonald's bị lỗi "ảo giác" (hallucination) dẫn đến chốt sai đơn hàng.
*   **Giải pháp:** Tạo ra một chatbot AI đặt hàng đa kênh (tập trung vào Zalo), giúp khách hàng đặt món trực tiếp qua cuộc hội thoại tự nhiên mà không cần chuyển đổi ứng dụng.
*   **Công nghệ & Chi phí:** Đội sử dụng Tiny Fish để cào dữ liệu từ web KFC, sử dụng **Agent Core** để hệ thống có bộ nhớ (ghi nhớ lịch sử đặt hàng của khách). Hệ thống có độ trễ chỉ 3-5 giây và chi phí cực rẻ, chỉ khoảng 0.006 đô la Mỹ cho mỗi đơn hàng.

**3. Đội Signal Scout (Giải Nhì) - Dự án Phân tích chiến lược kinh doanh**
*   **Vấn đề:** Thay vì chỉ tập trung vào công nghệ đại trà, đội muốn giải quyết bài toán nghiệp vụ thực tế là thu thập các tín hiệu kinh doanh rời rạc của công ty đối thủ (báo cáo tài chính, tọa đàm cổ đông).
*   **Giải pháp:** Xây dựng hệ thống thu thập thông tin đối thủ, kết nối chúng lại để dự báo tỷ suất sinh lời (ROI) và rủi ro nếu công ty của người dùng áp dụng chiến lược tương tự.
*   **Công nghệ:** Hệ thống kiến trúc chạy trên AWS với Amplify, Cognito. Dùng Agent Core điều phối các Subagent. Dùng Tiny Fish và Apify để thu thập dữ liệu web, sau đó dùng Bedrock Guardrail và LlamaIndex để chấm điểm, phân tích dữ liệu nhằm tránh hiện tượng ảo giác AI.

**4. Đội Team Plan - Dự án Trợ lý AI cho Solution Architect (SA)**
*   **Vấn đề:** Các kỹ sư giải pháp (SA) thường bị áp lực khi khách hàng yêu cầu gấp một bản vẽ kiến trúc hệ thống và bảng chi phí chỉ trong 1-2 ngày, thậm chí là ngay trong đêm.
*   **Giải pháp:** Xây dựng một ứng dụng nhận yêu cầu bằng ngôn ngữ tự nhiên từ người dùng. AI sẽ tự động phân tích, vẽ sơ đồ kiến trúc trên Draw.io, tính toán chi phí và xuất ra các đoạn code (Terraform/CloudFormation) để tự động triển khai hạ tầng.
*   **Công nghệ:** Kiểm soát chặt chẽ luồng workflow và context. Hệ thống sẽ chặn các dịch vụ không được phép sử dụng (black list) ngay từ đầu ra để đảm bảo AI tuân thủ đúng template nội bộ của doanh nghiệp.

**5. Đội 3K - Dự án Sheper (Quản lý luồng đám đông)**
*   **Vấn đề:** Sự ùn tắc con người tại các sân bay, siêu thị hoặc nơi tổ chức sự kiện.
*   **Giải pháp:** Xây dựng hệ thống camera giám sát kết hợp AI để tự động theo dõi, phát hiện các khu vực đang hoặc sắp bị ùn tắc và điều phối nhân sự hỗ trợ.
*   **Công nghệ:** Sử dụng Kinesis Video Stream, Fargate. Tích hợp mô hình YOLO để nhận diện người và ByteTrack để gắn ID theo dõi vật thể. Dữ liệu được đưa vào Agent kết nối với Amazon Bedrock để AI tính toán và đưa ra gợi ý giải quyết.
*   **Kinh nghiệm:** Đội chia sẻ những kỷ niệm thức trắng đêm, lỗi sơ đẳng như đẩy nhầm file .env lên GitHub và nhấn mạnh tầm quan trọng của việc kiểm soát phạm vi dự án (scope) vừa đủ trong các cuộc thi Hackathon.

**6. Đội Six Pillar - Dự án Adaptive Workflow Engine (Phòng chống rửa tiền)**
*   **Vấn đề:** Các hệ thống chống rửa tiền truyền thống sinh ra 90-95% cảnh báo sai, khiến các chuyên viên phân tích dữ liệu tốn đến hàng giờ đồng hồ để rà soát thủ công một cách mệt mỏi.
*   **Giải pháp:** Xây dựng hệ thống AI hỗ trợ điều tra các giao dịch tài chính bằng cách tự động kiểm tra hồ sơ (KYC), dòng tiền, đối chiếu luật và tạo ra báo cáo bằng chứng. 
*   **Công nghệ:** Kiến trúc gồm 3 lớp. Lớp 1 dùng mô hình Machine Learning (XGBoost), Kinesis và Lambda để lọc nhanh giao dịch. Lớp 2 dùng Step Functions gọi các Agent để truy xuất thông tin chuyên sâu. Lớp 3 là giao diện để con người đưa ra quyết định cuối cùng. Hệ thống tích hợp bảo mật cấp doanh nghiệp với KMS, Security Hub và X-Ray để truy vết và bảo vệ dữ liệu.

---

### Kết quả đạt được
- Nắm vững cách kết hợp giữa mô hình Agentic AI với hạ tầng đám mây AWS.
- Hiểu rõ triết lý "Done is better than perfect" trong các kỳ Hackathon.

---

### Ứng Dụng Vào Công Việc
- Áp dụng Agentic AI vào các dự án cá nhân để tự động hóa chuỗi hành động.
- Quản lý tốt phạm vi dự án (scope) trong các lần làm việc nhóm tương lai.

---

### Trải nghiệm trong event
- Trải nghiệm cảm xúc bùng nổ, thức đêm debug đến sáng và vỡ òa khi demo thành công.

#### Một số hình ảnh khi tham gia sự kiện
<div style="display: flex; gap: 20px; flex-wrap: wrap; justify-content: center;">
  <img src="/images/4-Events/4.3-hackathon-sharing/hackathon1.jpg" style="width: 45%; height: 250px; object-fit: cover;">
  <img src="/images/4-Events/4.3-hackathon-sharing/hackathon2.jpg" style="width: 45%; height: 250px; object-fit: cover;">
</div>
