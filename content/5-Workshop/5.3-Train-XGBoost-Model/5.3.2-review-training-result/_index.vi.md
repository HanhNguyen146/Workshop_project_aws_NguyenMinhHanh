---
title: "Kiểm tra kết quả huấn luyện"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 5.3.2. </b> "
---


Sau khi Training Job được tạo, SageMaker sẽ tự động thực hiện quá trình huấn luyện.

## Theo dõi trạng thái

Trong trang Training Jobs, trạng thái sẽ lần lượt chuyển thành

```
Starting

↓

In Progress

↓

Completed
```

> **Hình 1**
>
>![Figure 1](/images/5-Workshop/5.5/review-training-result/status.png)
>![Figure 1](/images/5-Workshop/5.5/review-training-result/status1.png)
---

## Kiểm tra CloudWatch Logs

Chọn tab

```
View logs
```

CloudWatch sẽ hiển thị toàn bộ log trong quá trình huấn luyện.

Có thể theo dõi:

- Loss
- Accuracy
- AUC
- Training Time

> **Hình 2**
>
> ![Figure 2](/images/5-Workshop/5.5/review-training-result/cloudwatch-log.png)

---

## Kiểm tra Model Artifact

Sau khi Training Job hoàn thành, SageMaker sẽ lưu mô hình tại Amazon S3.

Ví dụ

```
model.tar.gz
```

> **Hình 3**
>
> ![Figure 3](/images/5-Workshop/5.5/review-training-result/model-artifact.png)

---

## Kết quả

Training Job hoàn thành thành công và mô hình đã được lưu trong Amazon S3.

Ở chương tiếp theo, chúng ta sẽ sử dụng mô hình này để triển khai **Amazon SageMaker Endpoint**, phục vụ dự đoán lỗi thiết bị SCADA theo thời gian thực.