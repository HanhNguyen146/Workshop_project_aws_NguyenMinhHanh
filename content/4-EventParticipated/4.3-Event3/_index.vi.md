---
title: "Event 3"
date: 2026-07-11
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Bài thu hoạch “Bảo mật, Monitoring & Chứng chỉ AWS”

### Mục Đích Của Sự Kiện

- Tìm hiểu lộ trình ôn thi chứng chỉ AWS Cloud Practitioner.
- Khám phá giải pháp tự động hóa kiểm thử bảo mật (Pentest) bằng AI.
- Nhận thức tầm quan trọng của hệ thống giám sát (Monitoring) và SLA đối với trải nghiệm người dùng.

### Danh Sách Diễn Giả

- Anh Ngô Lê Tân Huy
- Anh Thịnh Nguyễn
- Anh Nguyễn Huỳnh Sơn

---

### Nội Dung Nổi Bật

Dựa vào các tài liệu bạn cung cấp, dưới đây là liệt kê chi tiết nội dung của 3 phần chia sẻ:

**Phần 1: Lộ trình chinh phục chứng chỉ AWS Cloud Practitioner**
*   **Diễn giả:** Ngô Lê Tân Huy.
*   **Tổng quan bài thi:** Đây là chứng chỉ nền tảng, tập trung vào cái nhìn tổng quan (big-picture) mà không yêu cầu người thi phải biết code hay cấu hình hệ thống sâu. Bài thi gồm 65 câu trắc nghiệm, kéo dài 90 phút (người không dùng tiếng Anh bản ngữ được cộng thêm 30 phút), với điểm đỗ là 700/1000 và có giá trị trong 3 năm.
*   **Cấu trúc bài thi (4 Domains):**
    *   *Domain 1 - Cloud Concepts (24%):* Không đi sâu vào kỹ thuật mà tập trung vào tư duy chuyển đổi số, 6 lợi ích của AWS Cloud, AWS Well-Architected Framework (WAF), AWS Cloud Adoption Framework (CAF) và Mô hình trách nhiệm chia sẻ (Shared Responsibility Model).
    *   *Domain 2 - Security and Compliance (30%):* Dịch vụ quản lý danh tính (IAM) với nguyên tắc đặc quyền tối thiểu, sự khác biệt giữa Security Groups và NACLs, các dịch vụ chống DDoS (AWS Shield, WAF) và báo cáo tuân thủ (AWS Artifact).
    *   *Domain 3 - Cloud Technology and Services (34%):* Kiến thức về hạ tầng toàn cầu (Region, AZ, Edge), dịch vụ máy tính (EC2, Lambda), lưu trữ/cơ sở dữ liệu (S3, EBS, RDS, DynamoDB...) và mạng lưới (VPC, Route 53).
    *   *Domain 4 - Billing, Pricing, and Support (12%):* Các mô hình giá của EC2 (On-Demand, Spot...), công cụ quản lý chi phí (AWS Cost Explorer, Budgets) và các gói hỗ trợ của AWS.
*   **Kinh nghiệm ôn tập & đi thi:** 
    *   *Ôn tập:* Nên áp dụng phương pháp "Map Keyword Thinking" (gắn mỗi dịch vụ với 1-2 từ khóa thực tế), tập trung phân tích kỹ lý do các câu hỏi sai khi thi thử và nên thực hành trực tiếp trên AWS Free Tier.
    *   *Đi thi:* Dùng phương pháp loại trừ (thường có 2 đáp án hoàn toàn bịa đặt), không nên nghĩ quá phức tạp (Don't overthink), cẩn thận với các từ khóa bẫy trong tiếng Anh như "Not", "Least cost" và sử dụng tính năng "Flag for review" để đánh dấu các câu chưa chắc chắn. 

**Phần 2: Bảo mật ứng dụng Web với AWS Security Agent**
*   **Diễn giả:** Thịnh Nguyễn (Nguyen Tuan Thinh).
*   **Nút thắt trong bảo mật:** Việc kiểm thử xâm nhập (pentest) thủ công hiện tại mất nhiều thời gian (nhiều tuần), đắt đỏ (5.000 - 20.000 USD/lần) và mức độ bao phủ phụ thuộc vào kỹ năng hay tâm trạng của người làm.
*   **Giải pháp - Frontier Agent:** Đây là tác tử tự chủ được hỗ trợ bởi Amazon Bedrock, có khả năng lên kế hoạch và thực thi bảo mật mà không cần con người can thiệp. Các giai đoạn bao gồm:
    *   *Design Review (Đánh giá thiết kế):* Phân tích tài liệu kiến trúc trước khi viết code để xem xét độ tuân thủ, miễn phí 200 lượt/tháng.
    *   *Code Security Review (Đánh giá bảo mật mã nguồn):* Tích hợp trực tiếp vào GitHub/GitLab Pull Requests để quét lỗ hổng và gợi ý bản vá lỗi code, miễn phí 1.000 lượt/tháng.
    *   *Automated Pentesting (Pentest tự động):* Tấn công thực tế vào ứng dụng đang chạy bằng các chuỗi khai thác nhiều bước và cung cấp bằng chứng rõ ràng.
*   **Chi phí:** Sau 2 tháng dùng thử miễn phí, chi phí là 50 USD/giờ tác vụ. Một case study thực tế cho thấy tổng chi phí tốn khoảng 1.500 - 2.500 USD, được xem là một "món hời" so với việc thuê đội ngũ pentest giá 10.000 USD.
*   **Hạn chế:** Hệ thống sẽ bị chặn đứng bởi các lớp xác thực (MFA, sinh trắc học, mTLS), khó phát hiện các lỗi lỗ hổng logic nghiệp vụ và có thể đốt số giờ tác vụ (tiền) rất nhanh với các ứng dụng phức tạp, do đó cần phải giám sát chặt chẽ.

**Phần 3: SLA và Giám sát (Monitoring)**
*   **Diễn giả:** Nguyễn Huỳnh Sơn.
*   **Vai trò của SLA & Monitoring:** SLA (Thỏa thuận cấp độ dịch vụ) giúp định hình các kỳ vọng và quản lý rủi ro. Việc giám sát nằm trong khâu quản lý rủi ro nhằm phát hiện sớm các vấn đề trước khi ảnh hưởng của SLA trở thành lời phàn nàn từ khách hàng, hoạt động theo vòng lặp: Nhận diện -> Giám sát -> Phản hồi -> Cải thiện.
*   **Mô hình tháp giám sát:** Theo thứ tự từ trên xuống: Trải nghiệm khách hàng -> Yếu tố kinh doanh -> Ứng dụng -> Cơ sở hạ tầng -> Nhà cung cấp Cloud. Việc chỉ giám sát phần cứng từ dưới lên là không đủ.
*   **Nghịch lý Giám sát:** "Cơ sở hạ tầng khỏe mạnh không đồng nghĩa với trải nghiệm người dùng vui vẻ". 
    *   Trong ví dụ demo thực tế: Các chỉ số máy chủ (CPU) có thể vẫn rất xanh ở mức 18% và Health check (kiểm tra tiến trình App) báo "200 OK", nhưng kết nối Database bị lỗi khiến người dùng không thể đăng nhập (tỷ lệ đăng nhập thành công từ 100% rớt xuống 0%).
*   **Luồng cảnh báo (Alerting flow):** Thông tin giám sát chỉ có giá trị khi nó báo trước lúc khách hàng phàn nàn. Luồng cơ bản là: Chỉ số riêng (Custom metric) -> Đặt cảnh báo (CloudWatch Alarm) vượt ngưỡng -> Mạng lưới phân phối (SNS Topic) -> Thông báo qua Email / Slack.
*   **Bài học cốt lõi:** Các chỉ số hạ tầng không thể nói lên toàn bộ câu chuyện, bạn cần phải biết rõ người dùng đang làm gì (đăng nhập, mua hàng...). AWS chỉ cam kết SLA bảo đảm nền tảng đám mây, còn người thiết kế hệ thống phải tự chịu trách nhiệm về trải nghiệm thực tế của khách hàng.

---

### Kết quả đạt được

- Lên được kế hoạch ôn thi chứng chỉ AWS bài bản.
- Hiểu được giá trị của việc đặt các chỉ số giám sát (metrics) đúng chỗ.

---

### Ứng Dụng Vào Công Việc

- Cấu hình cơ bản CloudWatch cho ứng dụng cá nhân để nhận cảnh báo sớm.
- Bắt đầu ôn tập chứng chỉ Cloud Practitioner.

---

### Trải nghiệm trong event

- Ấn tượng mạnh với khả năng của AI khi có thể đóng vai trò như một chuyên gia bảo mật để thâm nhập hệ thống.

#### Một số hình ảnh khi tham gia sự kiện

<div style="display: flex; justify-content: center;">
  <img src="/images/4-Events/event3/11_7.jpg" alt="Sự kiện" style="width: 50%; height: 300px; object-fit: cover;">
  <img src="/images/4-Events/event3/3.png" alt="Sự kiện" style="width: 50%; height: 300px; object-fit: cover;">
</div>
