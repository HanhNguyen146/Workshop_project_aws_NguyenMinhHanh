---
title: "Invoke Endpoint"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---


In this section, you will test the deployed Amazon SageMaker Endpoint by sending sample SCADA sensor data and reviewing the prediction results.

Amazon SageMaker Endpoint provides a secure HTTPS endpoint that supports real-time inference. Applications can send requests through the SageMaker Runtime API, and the deployed machine learning model returns prediction results within a few milliseconds.

By the end of this section, you will learn how to:

- Test the endpoint directly from the Amazon SageMaker Console.
- Invoke the endpoint using the SageMaker Runtime API.
- Interpret the prediction results returned by the model.

## Contents

1. [Review Prediction Results](5.5.1-view-prediction/)