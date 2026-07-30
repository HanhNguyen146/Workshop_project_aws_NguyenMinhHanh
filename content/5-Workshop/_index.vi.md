---
title: "Workshop"
date: 2024-07-22
weight: 5
chapter: false
pre: " <b> 5. </b> "
---



# SCADA Fault Prediction Platform sử dụng Amazon SageMaker

#### Tổng quan

Amazon SageMaker là dịch vụ Machine Learning được quản lý hoàn toàn trên AWS, giúp xây dựng, huấn luyện, triển khai và giám sát mô hình học máy một cách nhanh chóng mà không cần quản lý hạ tầng phức tạp. Kết hợp với các dịch vụ như Amazon S3, AWS Lambda, Amazon API Gateway, Amazon CloudWatch và Amazon SNS, SageMaker cho phép xây dựng một quy trình MLOps hoàn chỉnh từ xử lý dữ liệu đến triển khai mô hình trong môi trường thực tế.

Trong workshop này, bạn sẽ xây dựng một hệ thống dự đoán lỗi thiết bị công nghiệp dựa trên dữ liệu SCADA sử dụng bộ dữ liệu công khai **SKAB (Skoltech Anomaly Benchmark)**. Bạn sẽ lần lượt tải dữ liệu lên Amazon S3, tiền xử lý dữ liệu bằng SageMaker Processing, huấn luyện mô hình XGBoost, triển khai mô hình dưới dạng SageMaker Endpoint, thực hiện dự đoán thời gian thực và giám sát hệ thống bằng Amazon CloudWatch và Amazon SNS.

Workshop giúp người học hiểu toàn bộ quy trình triển khai một mô hình Machine Learning trên nền tảng AWS theo hướng MLOps, từ chuẩn bị dữ liệu đến triển khai và giám sát mô hình trong môi trường sản xuất.

#### Nội dung

1. [Tổng quan](5.1-Overview/)
2. [Điều kiện tiên quyết](5.2-Prerequisites/)
3. [Tải bộ dữ liệu lên Amazon S3](5.3-Upload-S3/)
4. [Tiền xử lý dữ liệu bằng SageMaker](5.4-Processing/)
5. [Huấn luyện mô hình XGBoost](5.5-Training/)
6. [Triển khai SageMaker Endpoint](5.6-Deployment/)
7. [Thực hiện dự đoán với Endpoint](5.7-Invoke/)
8. [Giám sát Endpoint bằng CloudWatch](5.8-CloudWatch/)
9. [Tạo thông báo bằng Amazon SNS (Nâng cao)](5.9-SNS/)
10. [Dọn dẹp tài nguyên](5.10-Cleanup/)