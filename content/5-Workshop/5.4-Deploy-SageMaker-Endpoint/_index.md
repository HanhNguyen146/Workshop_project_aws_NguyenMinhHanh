---
title: "Deploy SageMaker Endpoint"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---


After successfully training the XGBoost model, the next step is to deploy it as an **Amazon SageMaker Endpoint** for real-time inference.

Amazon SageMaker Endpoint is a fully managed inference service that hosts machine learning models behind a REST API. Client applications can send prediction requests and receive inference results within milliseconds.

During deployment, SageMaker automatically provisions the required infrastructure, loads the trained model from Amazon S3, creates an HTTPS endpoint, and keeps the service available for online predictions.

After completing this chapter, you will be able to:

- Create a SageMaker Model.
- Configure an Endpoint Configuration.
- Deploy a SageMaker Endpoint.
- Verify that the endpoint status becomes **InService**.

## Contents


1. [Create Endpoint Configuration](5.4.1-create-endpoint-config/)