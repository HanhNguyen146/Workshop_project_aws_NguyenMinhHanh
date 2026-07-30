---
title: "Train XGBoost Model"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---



In this section, we will use **Amazon SageMaker Training Jobs** to train an **XGBoost** model using the preprocessed SCADA dataset generated in the previous steps.

Amazon SageMaker provides a fully managed machine learning environment, allowing users to train models without provisioning or managing servers manually. By specifying the input dataset, training algorithm, and hyperparameters, SageMaker automatically provisions the required compute resources, executes the training process, and stores the trained model in **Amazon S3**.

After completing this chapter, you will be able to:

- Create an **Amazon SageMaker Training Job**.
- Configure **XGBoost hyperparameters**.
- Monitor the training process using **Amazon CloudWatch Logs**.
- Review the training results and locate the generated model artifact in Amazon S3.

## Contents

1. [Create SageMaker Training Job](5.3.1-Create-Training-Job/)
2. [Review Training Results](5.3.2-review-training-result/)