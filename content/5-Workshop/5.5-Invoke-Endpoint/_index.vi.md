---
title: "Kiểm thử Endpoint"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---



Trong phần này, chúng ta sẽ kiểm tra Endpoint đã được triển khai bằng cách gửi dữ liệu cảm biến SCADA và xem kết quả dự đoán của mô hình.

Amazon SageMaker Endpoint cung cấp một địa chỉ HTTPS để thực hiện dự đoán theo thời gian thực (Real-time Inference). Các ứng dụng có thể gửi dữ liệu thông qua SageMaker Runtime API và nhận kết quả dự đoán chỉ trong vài mili giây.

Sau khi hoàn thành chương này, bạn sẽ có thể:

- Kiểm thử Endpoint trực tiếp trên Amazon SageMaker Console.
- Gửi yêu cầu dự đoán bằng SageMaker Runtime API.
- Phân tích kết quả dự đoán do mô hình trả về.

## Nội dung

1. [Xem kết quả dự đoán](5.5.1-view-prediction/)