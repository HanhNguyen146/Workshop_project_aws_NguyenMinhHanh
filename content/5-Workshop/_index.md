---
title: "Workshop"
date: 2026-07-22
weight: 5
chapter: false
pre: " <b> 5. </b> "
---


# SCADA Fault Prediction Platform using Amazon SageMaker

#### Overview

Amazon SageMaker is a fully managed machine learning service that enables developers and data scientists to build, train, deploy, and monitor machine learning models at scale. Combined with other AWS services such as Amazon S3, AWS Lambda, Amazon API Gateway, Amazon CloudWatch, and Amazon SNS, it provides a complete MLOps workflow with minimal infrastructure management.

In this workshop, you will learn how to build an end-to-end fault prediction system for industrial SCADA data using the public SKAB (Skoltech Anomaly Benchmark) dataset. You will upload datasets to Amazon S3, preprocess data using SageMaker Processing Jobs, train an XGBoost model, deploy a real-time SageMaker Endpoint, invoke predictions through an API, and monitor the deployed model using CloudWatch and SNS.

This workshop demonstrates the complete lifecycle of a machine learning application, from data preparation to production deployment and monitoring.

#### Content

1. [Overview](5.1-Overview/)
2. [Prerequisites](5.2-Prerequisites/)
3. [Train XGBoost Model](5.3-Training/)
4. [Deploy SageMaker Endpoint](5.4-Deployment/)
5. [Invoke Endpoint](5.5-Invoke/)
6. [Monitor Endpoint with CloudWatch](5.6-CloudWatch/)
7. [Create SNS Notification (Bonus)](5.7-SNS/)
8. [Clean Up](5.8-Cleanup/)