---
title: "Huấn luyện mô hình XGBoost"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---



Trong phần này, chúng ta sẽ sử dụng **Amazon SageMaker Training Job** để huấn luyện mô hình **XGBoost** trên tập dữ liệu SCADA đã được xử lý ở các bước trước.

Amazon SageMaker cung cấp môi trường huấn luyện được quản lý hoàn toàn (Fully Managed), giúp người dùng không cần tự cấu hình máy chủ hoặc cài đặt môi trường học máy. Chỉ cần cung cấp dữ liệu đầu vào, thuật toán và các tham số huấn luyện, SageMaker sẽ tự động tạo tài nguyên tính toán, thực hiện quá trình huấn luyện và lưu mô hình đã học vào **Amazon S3**.

Sau khi hoàn thành chương này, bạn sẽ:

- Tạo một **SageMaker Training Job**.
- Cấu hình các **hyperparameters** cho thuật toán XGBoost.
- Theo dõi quá trình huấn luyện thông qua **Amazon CloudWatch Logs**.
- Kiểm tra kết quả huấn luyện và mô hình được lưu trên Amazon S3.

## Nội dung

1. [Tạo SageMaker Training Job](5.3.1-Create-Training-Job/)
2. [Kiểm tra kết quả huấn luyện](5.3.2-review-training-result/)
