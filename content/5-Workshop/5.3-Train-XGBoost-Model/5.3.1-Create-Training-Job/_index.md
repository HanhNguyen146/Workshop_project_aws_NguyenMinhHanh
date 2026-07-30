---
title: "Create SageMaker Training Job"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 5.3.1. </b> "
---


In this step, we will create an **Amazon SageMaker Training Job** to train the XGBoost model using the processed SCADA dataset stored in Amazon S3.

A SageMaker Training Job automatically:

- Creates the training environment.
- Downloads the dataset from Amazon S3.
- Executes the XGBoost algorithm.
- Stores the trained model after completion.

## Step 1. Open Amazon SageMaker

Log in to the AWS Management Console and search for **Amazon SageMaker AI**.

> **Figure 1**
>
> ![Figure 1](/images/5-Workshop/5.5/create-training-job/sagemaker-home.png)

---

## Step 2. Navigate to Training Jobs

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

At this point, the training environment has been configured and is ready for dataset and hyperparameter configuration.