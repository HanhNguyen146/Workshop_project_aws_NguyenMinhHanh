---
title: "Blog 2"
date: 2026-07-26
weight: 2
draft: false
pre: " <b> 3.2. </b> "

---
# Giám sát SageMaker Endpoint với Amazon CloudWatch

Việc triển khai một mô hình Machine Learning chỉ là bước khởi đầu trong vòng đời của hệ thống. Sau khi mô hình được triển khai dưới dạng **Amazon SageMaker Endpoint**, việc giám sát liên tục là yếu tố quan trọng để đảm bảo dịch vụ suy luận (Inference) luôn hoạt động ổn định, đáng tin cậy và đạt hiệu năng cao.

**Amazon CloudWatch** là dịch vụ giám sát mặc định của AWS, cho phép thu thập, lưu trữ và phân tích **Metrics**, **Logs**, **Events** và **Alarms** từ các tài nguyên AWS. Khi được tích hợp với Amazon SageMaker, CloudWatch giúp theo dõi hiệu năng Endpoint theo thời gian thực, nhanh chóng phát hiện sự cố và tự động gửi cảnh báo khi hệ thống xảy ra bất thường.

Kiến trúc dưới đây minh họa cách Amazon CloudWatch hoạt động cùng với Amazon SageMaker và Amazon SNS.

---

## Tại sao cần giám sát SageMaker Endpoint?

Sau khi triển khai, SageMaker Endpoint sẽ liên tục tiếp nhận các yêu cầu dự đoán từ người dùng hoặc các ứng dụng khác. Nếu không có cơ chế giám sát, các vấn đề như độ trễ tăng cao, lỗi suy luận hoặc tài nguyên hệ thống bị quá tải có thể không được phát hiện kịp thời, ảnh hưởng trực tiếp đến chất lượng dịch vụ.

Amazon CloudWatch giúp người quản trị theo dõi trạng thái hoạt động của Endpoint theo thời gian thực và phát hiện sớm các dấu hiệu bất thường trước khi chúng gây ảnh hưởng đến hệ thống.

Một số khả năng nổi bật của CloudWatch gồm:

- Giám sát hiệu năng theo thời gian thực.
- Tự động thu thập các chỉ số hoạt động (Metrics).
- Quản lý và lưu trữ nhật ký hệ thống (Logs).
- Tạo cảnh báo (Alarms) dựa trên các ngưỡng được cấu hình.
- Tích hợp với Amazon SNS để gửi thông báo tự động.

---

## Theo dõi Metrics của Endpoint

Amazon SageMaker tự động gửi các chỉ số hoạt động của Endpoint đến Amazon CloudWatch.

Một số Metrics quan trọng bao gồm:

- **Invocation Count** – Số lượng yêu cầu dự đoán được gửi đến Endpoint.
- **Model Latency** – Thời gian mô hình xử lý và trả về kết quả dự đoán.
- **Invocation Errors** – Số lượng yêu cầu suy luận bị lỗi.
- **CPU Utilization** – Mức sử dụng CPU của môi trường suy luận.
- **Memory Utilization** – Mức sử dụng bộ nhớ trong quá trình thực thi mô hình.

Thông qua các chỉ số này, người quản trị có thể đánh giá hiệu năng của Endpoint, theo dõi xu hướng sử dụng và phát hiện các vấn đề về tài nguyên hoặc hiệu suất.

---

## Theo dõi Logs

Bên cạnh Metrics, CloudWatch còn lưu trữ toàn bộ nhật ký được tạo ra từ môi trường suy luận của SageMaker.

Các thông tin thường xuất hiện trong Logs bao gồm:

- Thông tin khởi động Endpoint.
- Yêu cầu dự đoán (Inference Request).
- Kết quả dự đoán.
- Các ngoại lệ (Exceptions) phát sinh trong quá trình xử lý.
- Nhật ký hệ thống và Container.

CloudWatch Logs giúp việc phân tích nguyên nhân lỗi, kiểm tra quá trình xử lý và gỡ lỗi ứng dụng trở nên dễ dàng hơn.

---

## Tạo CloudWatch Alarm

CloudWatch cho phép tạo các cảnh báo dựa trên những ngưỡng được định nghĩa trước.

Ví dụ, có thể cấu hình Alarm khi:

- Độ trễ (Model Latency) vượt quá giá trị cho phép.
- Số lượng lỗi suy luận tăng bất thường.
- CPU Utilization duy trì ở mức quá cao trong một khoảng thời gian.

Khi điều kiện được đáp ứng, trạng thái của Alarm sẽ chuyển từ **OK** sang **ALARM**, từ đó kích hoạt các hành động đã được cấu hình.

---

## Tích hợp CloudWatch với Amazon SNS

Một trong những tính năng hữu ích của CloudWatch là khả năng tích hợp trực tiếp với **Amazon SNS (Simple Notification Service)**.

Khi Alarm được kích hoạt:

1. CloudWatch phát hiện chỉ số vượt ngưỡng.
2. Alarm chuyển sang trạng thái **ALARM**.
3. CloudWatch gửi thông báo đến Amazon SNS Topic.
4. Amazon SNS phân phối thông báo đến những người đã đăng ký.

Amazon SNS hỗ trợ nhiều hình thức gửi thông báo như:

- Email
- SMS
- HTTP/HTTPS Endpoint
- AWS Lambda
- Amazon SQS

Nhờ đó, quản trị viên có thể nhanh chóng nhận được cảnh báo và xử lý sự cố kịp thời.

---

## Lợi ích của Amazon CloudWatch

Việc sử dụng Amazon CloudWatch cùng với Amazon SageMaker mang lại nhiều lợi ích như:

- Giám sát Endpoint theo thời gian thực.
- Thu thập tập trung Metrics và Logs.
- Phát hiện và xử lý sự cố nhanh chóng.
- Tự động gửi cảnh báo khi có bất thường.
- Nâng cao tính ổn định và độ sẵn sàng của hệ thống.
- Hỗ trợ quản lý và vận hành mô hình Machine Learning trong môi trường Production hiệu quả hơn.

---

## Kết luận

Amazon CloudWatch là một thành phần không thể thiếu trong quá trình vận hành các hệ thống Machine Learning trên AWS. Bằng cách thu thập Metrics, lưu trữ Logs, tạo Alarms và tích hợp với Amazon SNS để gửi thông báo tự động, CloudWatch giúp các mô hình được triển khai trên Amazon SageMaker luôn hoạt động ổn định, dễ dàng giám sát và nhanh chóng phát hiện các sự cố phát sinh.

Việc triển khai cơ chế giám sát không chỉ nâng cao độ tin cậy của hệ thống mà còn giúp giảm thời gian xử lý sự cố, tối ưu hiệu năng và đảm bảo chất lượng dịch vụ trong môi trường Production.