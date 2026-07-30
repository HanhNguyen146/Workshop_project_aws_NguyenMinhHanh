---
title: "Triển khai SageMaker Endpoint"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---


Sau khi mô hình XGBoost được huấn luyện thành công, bước tiếp theo là triển khai mô hình thành một **Amazon SageMaker Endpoint** để cung cấp khả năng dự đoán theo thời gian thực (Real-time Inference).

Amazon SageMaker Endpoint là dịch vụ triển khai mô hình học máy được quản lý hoàn toàn (Fully Managed). Dịch vụ này tự động khởi tạo hạ tầng, tải mô hình từ Amazon S3 và cung cấp một HTTPS Endpoint để các ứng dụng bên ngoài có thể gửi dữ liệu và nhận kết quả dự đoán.

Trong hệ thống SCADA Fault Prediction Platform, Endpoint đóng vai trò là thành phần trung tâm phục vụ dự đoán lỗi thiết bị. Các ứng dụng Web, API Gateway hoặc AWS Lambda đều có thể gửi dữ liệu cảm biến đến Endpoint để nhận kết quả dự đoán gần như tức thời.

Sau khi hoàn thành chương này, bạn sẽ:

- Tạo **Model** từ mô hình đã huấn luyện.
- Tạo **Endpoint Configuration**.
- Triển khai **SageMaker Endpoint**.
- Kiểm tra trạng thái Endpoint sau khi triển khai.

> **Lưu ý:** Endpoint là dịch vụ tính phí theo thời gian chạy. Sau khi hoàn thành Workshop, nên xóa Endpoint để tránh phát sinh chi phí.

## Nội dung


1. [Tạo Endpoint Configuration](5.4.1-create-endpoint-config/)
