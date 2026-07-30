---
title: "Prerequisites"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---


Before building and deploying the SCADA Fault Prediction Platform, several AWS resources and development environments need to be prepared. This section introduces the required permissions, AWS services, and initial configuration that will be used throughout the workshop.

After completing this section, you will have a fully configured environment for uploading datasets, training machine learning models, deploying SageMaker Endpoints, monitoring system performance, and configuring notification services.

---

## AWS Services

The following AWS services will be used throughout this workshop:

| Service | Purpose |
|----------|---------|
| Amazon S3 | Store datasets, processed data, and trained models |
| Amazon SageMaker | Data processing, model training, deployment, and inference |
| AWS IAM | Manage permissions for AWS resources |
| Amazon CloudWatch | Monitor endpoint metrics and logs |
| Amazon SNS | Send email notifications |
| AWS Lambda | Process prediction requests (optional) |
| Amazon API Gateway | Expose prediction APIs (optional) |

---

## Prerequisites

Before starting the workshop, ensure you have:

- An AWS account with sufficient permissions.
- Access to the AWS Management Console.
- Python 3.10 or later.
- Jupyter Notebook (optional).
- AWS CLI installed and configured.
- The SKAB dataset prepared for upload.

---

## Configure IAM Permissions

The IAM user or role used for this workshop must have permissions to access the required AWS services.

Required services include:

- Amazon SageMaker
- Amazon S3
- Amazon CloudWatch
- Amazon SNS
- AWS IAM
- Amazon ECR (for SageMaker containers)

For simplicity, the workshop can be completed using an AWS Academy Lab account or an administrator account.

> **Figure 1**

![IAM Permissions](/images/5-Workshop/5.2/iam-permission.png)

---

## Configure AWS Region

For consistency throughout this workshop, select the AWS Region that supports all required SageMaker services.

Example:

```
Singapore

ap-southeast-1
```

> **Figure 2**

![AWS Region](/images/5-Workshop/5.2/aws-region.png)

---

## Verify SageMaker Access

From the AWS Console, search for

```
Amazon SageMaker AI
```

Open the SageMaker dashboard and verify that the service is available.

> **Figure 3**

![SageMaker Home](/images/5-Workshop/5.2/sagemaker-home.png)

---

## Verify Amazon S3

Open

```
Amazon S3
```

Ensure you are able to create or access S3 buckets that will be used during the workshop.

> **Figure 4**

![Amazon S3](/images/5-Workshop/5.2/s3-console.png)

---

## Workshop Environment Ready

After completing the preparation steps, the environment is ready for the remaining chapters.

The following sections will guide you through the complete machine learning workflow:

- Upload the SKAB dataset to Amazon S3.
- Process the dataset using SageMaker Processing.
- Train an XGBoost model.
- Deploy a SageMaker Endpoint.
- Perform real-time predictions.
- Monitor the endpoint with CloudWatch.
- Configure SNS notifications.
- Clean up AWS resources.

You are now ready to begin building the **SCADA Fault Prediction Platform**.