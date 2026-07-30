---
title: "Blog 1"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---


# Triển khai và giám sát mô hình Machine Learning bằng Amazon SageMaker Endpoint, Amazon CloudWatch và Amazon SNS

Trong các dự án Machine Learning, việc xây dựng được một mô hình có độ chính xác cao chỉ là bước khởi đầu. Để mô hình có thể hoạt động ổn định trong môi trường thực tế, chúng ta cần triển khai (Deployment) và giám sát (Monitoring) liên tục nhằm đảm bảo hệ thống luôn sẵn sàng, phản hồi nhanh và cung cấp kết quả dự đoán đáng tin cậy.

AWS cung cấp nhiều dịch vụ được quản lý hoàn toàn giúp đơn giản hóa quy trình này. Amazon SageMaker Endpoint hỗ trợ triển khai mô hình để dự đoán theo thời gian thực, trong khi Amazon CloudWatch và Amazon SNS giúp giám sát hệ thống và gửi cảnh báo tự động khi có sự cố.

---

# Kiến trúc tổng quan

Sơ đồ dưới đây mô tả luồng xử lý yêu cầu dự đoán trong hệ thống.

![Overall Architecture](/images/3-Blogs/blog3/architecture.png)

Quy trình hoạt động gồm các bước:

- **Amazon API Gateway** tiếp nhận các yêu cầu từ ứng dụng hoặc người dùng.
- **AWS Lambda** xử lý và kiểm tra dữ liệu đầu vào.
- **Amazon SageMaker Endpoint** thực hiện dự đoán theo thời gian thực.
- **Amazon CloudWatch** thu thập log và các chỉ số hoạt động.
- **Amazon SNS** gửi cảnh báo khi CloudWatch phát hiện sự cố.

---

# Tại sao nên sử dụng SageMaker Endpoint?

Sau khi huấn luyện xong mô hình, chúng ta cần một cách hiệu quả để phục vụ việc dự đoán mà không phải tải mô hình thủ công mỗi lần sử dụng.

Amazon SageMaker Endpoint là dịch vụ triển khai mô hình được AWS quản lý hoàn toàn. Dịch vụ này tự động tạo hạ tầng cần thiết và cung cấp một Endpoint an toàn để các ứng dụng có thể gửi yêu cầu dự đoán.

Một số ưu điểm nổi bật gồm:

- Dự đoán theo thời gian thực.
- Tự động mở rộng tài nguyên.
- Độ sẵn sàng cao.
- Triển khai an toàn.
- Dễ dàng tích hợp với các dịch vụ AWS khác.


---

# Giám sát bằng Amazon CloudWatch

Sau khi triển khai mô hình, việc giám sát hệ thống là rất quan trọng để phát hiện sớm các vấn đề và đảm bảo Endpoint luôn hoạt động ổn định.

Amazon CloudWatch tự động thu thập nhiều chỉ số quan trọng như:

- Số lượng yêu cầu dự đoán (Invocation Count)
- Thời gian phản hồi của mô hình (Model Latency)
- Mức sử dụng CPU
- Mức sử dụng bộ nhớ
- Tỷ lệ lỗi của Endpoint

Những thông tin này giúp nhóm phát triển đánh giá hiệu năng của mô hình và nhanh chóng phát hiện các bất thường trước khi ảnh hưởng đến người dùng.

Một số chỉ số thường được theo dõi:

| Chỉ số | Ý nghĩa |
|---------|----------|
| InvocationCount | Tổng số yêu cầu dự đoán |
| ModelLatency | Thời gian xử lý của mô hình |
| CPUUtilization | Mức sử dụng CPU |
| MemoryUtilization | Mức sử dụng bộ nhớ |
| Invocation5XXErrors | Số lượng lỗi phía máy chủ |

Ngoài các chỉ số, CloudWatch còn lưu trữ log từ AWS Lambda và SageMaker Endpoint, giúp việc phân tích và xử lý lỗi trở nên dễ dàng hơn.

---

# Gửi cảnh báo tự động bằng Amazon SNS

Trong các hệ thống thực tế, việc nhận cảnh báo ngay khi có sự cố là rất cần thiết.

Amazon SNS có thể kết hợp với CloudWatch Alarm để gửi thông báo tự động khi các chỉ số vượt quá ngưỡng đã thiết lập.

Ví dụ:

- Thời gian phản hồi của Endpoint tăng quá cao.
- Tỷ lệ lỗi vượt quá mức cho phép.
- Endpoint ngừng hoạt động.



Amazon SNS hỗ trợ nhiều hình thức thông báo như:

- Email
- SMS
- AWS Chatbot
- HTTPS Endpoint

Nhờ đó, quản trị viên có thể nhanh chóng phát hiện và xử lý sự cố trước khi ảnh hưởng đến chất lượng dịch vụ.

---

# Các khuyến nghị khi triển khai

Để hệ thống hoạt động hiệu quả và ổn định, nên áp dụng một số thực hành tốt sau:

- Quản lý phiên bản mô hình bằng SageMaker Model Registry.
- Bật CloudWatch Logs cho Lambda và SageMaker Endpoint.
- Thiết lập CloudWatch Alarm cho độ trễ và tỷ lệ lỗi.
- Sử dụng Amazon SNS để gửi cảnh báo tự động.
- Xóa các Endpoint không còn sử dụng nhằm tiết kiệm chi phí.
- Lựa chọn loại máy chủ (Instance Type) phù hợp với nhu cầu xử lý.

---

# Lợi ích

Việc kết hợp Amazon SageMaker Endpoint, CloudWatch và SNS mang lại nhiều lợi ích:

- Triển khai mô hình đơn giản.
- Hỗ trợ dự đoán theo thời gian thực.
- Giám sát tập trung.
- Cảnh báo tự động khi có sự cố.
- Khả năng mở rộng cao.
- Dễ dàng tích hợp với các dịch vụ AWS.
- Giảm chi phí quản lý hạ tầng.

Kiến trúc này giúp các nhóm phát triển tập trung vào việc cải thiện mô hình Machine Learning thay vì phải dành nhiều thời gian quản lý hệ thống.

---

# Kết luận

Triển khai mô hình chỉ là một bước trong toàn bộ vòng đời của hệ thống Machine Learning. Việc giám sát liên tục giúp đảm bảo mô hình luôn hoạt động ổn định, có khả năng phản hồi nhanh và tối ưu chi phí vận hành.

Amazon SageMaker Endpoint cung cấp dịch vụ dự đoán theo thời gian thực, CloudWatch giúp theo dõi hiệu năng hệ thống, còn Amazon SNS hỗ trợ gửi cảnh báo khi phát hiện sự cố. Sự kết hợp của ba dịch vụ này tạo nên một giải pháp triển khai Machine Learning mạnh mẽ, tin cậy và phù hợp cho các ứng dụng chạy trên nền tảng AWS.

---

# Tài liệu tham khảo

- AWS Documentation – Amazon SageMaker
- AWS Documentation – Amazon CloudWatch
- AWS Documentation – Amazon SNS