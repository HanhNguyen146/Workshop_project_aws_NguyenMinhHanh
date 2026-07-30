---
title: "Review Training Results"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 5.3.2. </b> "
---


After the training job has been created, Amazon SageMaker automatically performs the model training process.

## Monitor Training Status

The training job status changes through the following stages:

```
Starting

↓

In Progress

↓

Completed
```

> **Figure 1**
>
> ![Figure 1](/images/5-Workshop/5.5/review-training-result/status.png)
>![Figure 1](/images/5-Workshop/5.5/review-training-result/status1.png)
---

## View CloudWatch Logs

Select the training job and open the **View logs** option.

Amazon CloudWatch displays detailed logs generated during the training process, including:

- Training progress
- Evaluation metrics
- Training duration
- Resource utilization

> **Figure 2**
>
>![Figure 2](/images/5-Workshop/5.5/review-training-result/cloudwatch-log.png)

---

## Review the Model Artifact

Once the training job completes successfully, SageMaker stores the trained model in Amazon S3.

Example output:

```
model.tar.gz
```

> **Figure 3**
>
> ![Figure 3](/images/5-Workshop/5.5/review-training-result/model-artifact.png)

---

## Result

The training job has successfully completed, and the trained XGBoost model has been stored in Amazon S3.

In the next chapter, the trained model will be deployed as an **Amazon SageMaker Endpoint** to provide real-time fault prediction services for the SCADA system.