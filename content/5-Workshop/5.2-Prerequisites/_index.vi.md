---
title: "Các bước chuẩn bị"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---



Trước khi bắt đầu xây dựng và triển khai **SCADA Fault Prediction Platform**, chúng ta cần chuẩn bị môi trường AWS và kiểm tra các tài nguyên cần thiết để đảm bảo toàn bộ quy trình triển khai diễn ra thuận lợi.

Trong workshop này, người thực hiện sẽ sử dụng các dịch vụ của AWS để xây dựng một quy trình Machine Learning hoàn chỉnh, bao gồm lưu trữ dữ liệu, xử lý dữ liệu, huấn luyện mô hình, triển khai Endpoint, thực hiện dự đoán theo thời gian thực, giám sát hệ thống và cấu hình cảnh báo tự động.

Sau khi hoàn thành phần chuẩn bị, môi trường AWS sẽ sẵn sàng để thực hiện các chương tiếp theo của workshop.

---

## Các dịch vụ AWS sử dụng

Trong workshop này, chúng ta sẽ sử dụng các dịch vụ sau:

| Dịch vụ | Mục đích |
|----------|-----------|
| Amazon S3 | Lưu trữ bộ dữ liệu, dữ liệu đã xử lý và mô hình đã huấn luyện |
| Amazon SageMaker | Xử lý dữ liệu, huấn luyện, triển khai và dự đoán mô hình |
| AWS IAM | Quản lý quyền truy cập các dịch vụ AWS |
| Amazon CloudWatch | Giám sát Endpoint và thu thập Logs |
| Amazon SNS | Gửi email thông báo khi xảy ra cảnh báo |
| AWS Lambda *(tùy chọn)* | Xử lý các yêu cầu dự đoán |
| Amazon API Gateway *(tùy chọn)* | Cung cấp REST API cho hệ thống |

---

## Điều kiện tiên quyết

Trước khi bắt đầu workshop, hãy đảm bảo bạn đã chuẩn bị:

- Một tài khoản AWS có đủ quyền sử dụng các dịch vụ cần thiết.
- Có thể đăng nhập vào **AWS Management Console**.
- Python phiên bản **3.10** trở lên.
- AWS CLI đã được cài đặt và cấu hình (nếu sử dụng).
- Bộ dữ liệu **SKAB** để phục vụ quá trình huấn luyện mô hình.

---

## Cấu hình quyền IAM

Tài khoản AWS sử dụng trong workshop cần có quyền truy cập vào các dịch vụ được sử dụng trong đề tài.

Các quyền tối thiểu bao gồm:

- Amazon SageMaker
- Amazon S3
- Amazon CloudWatch
- Amazon SNS
- AWS IAM
- Amazon ECR (để sử dụng các container của SageMaker)

Đối với môi trường học tập, có thể sử dụng tài khoản **AWS Academy Learner Lab** hoặc tài khoản có quyền **Administrator** để thuận tiện trong quá trình thực hiện.

> **Hình 1**

![IAM Permission](/images/5-Workshop/5.2/iam-permission.png)

---

## Chọn AWS Region

Để đảm bảo các dịch vụ hoạt động ổn định và thống nhất trong suốt workshop, hãy lựa chọn Region hỗ trợ đầy đủ Amazon SageMaker.

Ví dụ:

```
Singapore

ap-southeast-1
```

> **Hình 2**

![AWS Region](/images/5-Workshop/5.2/aws-region.png)

---

## Kiểm tra Amazon SageMaker

Trên thanh tìm kiếm của **AWS Management Console**, tìm kiếm:

```
Amazon SageMaker AI
```

Mở trang quản lý của SageMaker và kiểm tra xem dịch vụ đã sẵn sàng sử dụng hay chưa.

> **Hình 3**

![Amazon SageMaker](/images/5-Workshop/5.2/sagemaker-home.png)

---

## Kiểm tra Amazon S3

Tiếp theo, mở dịch vụ:

```
Amazon S3
```

Đảm bảo tài khoản có thể tạo hoặc truy cập Bucket để lưu trữ dữ liệu của dự án.

Bucket này sẽ được sử dụng xuyên suốt workshop để lưu:

- Bộ dữ liệu SKAB
- Dữ liệu sau khi tiền xử lý
- Mô hình đã huấn luyện
- Kết quả đầu ra của SageMaker

> **Hình 4**

![Amazon S3](/images/5-Workshop/5.2/s3-console.png)

---

## Hoàn tất chuẩn bị

Sau khi hoàn thành các bước trên, môi trường AWS đã sẵn sàng để triển khai hệ thống **SCADA Fault Prediction Platform**.

Trong các chương tiếp theo, chúng ta sẽ lần lượt thực hiện toàn bộ quy trình xây dựng và triển khai mô hình Machine Learning trên AWS, bao gồm:

- Tải bộ dữ liệu **SKAB** lên Amazon S3.
- Tiền xử lý dữ liệu bằng SageMaker Processing.
- Huấn luyện mô hình **XGBoost**.
- Triển khai mô hình dưới dạng **SageMaker Endpoint**.
- Thực hiện dự đoán theo thời gian thực.
- Giám sát Endpoint bằng Amazon CloudWatch.
- Thiết lập cảnh báo tự động với Amazon SNS.
- Dọn dẹp tài nguyên sau khi hoàn thành workshop.

Sau khi hoàn thành phần chuẩn bị này, bạn đã sẵn sàng bắt đầu xây dựng và triển khai nền tảng **SCADA Fault Prediction Platform** trên AWS.