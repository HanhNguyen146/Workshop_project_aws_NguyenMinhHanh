---
title: "Tạo SageMaker Training Job"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 5.3.1. </b> "
---


Trong bước này, chúng ta sẽ tạo một **Amazon SageMaker Training Job** để huấn luyện mô hình XGBoost bằng tập dữ liệu SCADA đã được xử lý ở bước trước.

Training Job sẽ tự động:

- Khởi tạo máy chủ huấn luyện.
- Đọc dữ liệu từ Amazon S3.
- Chạy thuật toán XGBoost.
- Lưu mô hình sau khi hoàn thành.

## Thực hiện

### 1. Truy cập Amazon SageMaker

Từ AWS Console tìm kiếm **Amazon SageMaker AI**.

> **Hình 1**
>
> ![Figure 1](/images/5-Workshop/5.5/create-training-job/sagemaker-home.png)

---

### 2. Chọn Training Jobs

Code :

```
import argparse
import sagemaker
from sagemaker.sklearn.estimator import SKLearn


def main():
    parser = argparse.ArgumentParser()
    parser.add_argument('--bucket', type=str,
                        default='scada-fault-prediction')
    parser.add_argument('--role', type=str,
                        default='arn:aws:iam::036071344072:role/SageMakerExecutionRole-MLOps')
    args = parser.parse_args()

    print("Khởi động SageMaker Training Job...")

    sklearn_estimator = SKLearn(
        entry_point='src/train.py',
        role=args.role,
        instance_count=1,
        instance_type='ml.m5.large',
        framework_version='1.2-1',
        base_job_name='scada-gmm',
        hyperparameters={
            'n_components': '5'
        }
    )

    s3_train_data = f's3://{args.bucket}/features'
    print(f"[INFO] Nạp dữ liệu từ: {s3_train_data}")

    sklearn_estimator.fit({'train': s3_train_data})

    print("Training Job hoàn tất!")
    print(f"Model tại: {sklearn_estimator.model_data}")


if __name__ == '__main__':
    main()
```


Sau khi hoàn thành bước này, Training Job đã sẵn sàng để cấu hình dữ liệu đầu vào.