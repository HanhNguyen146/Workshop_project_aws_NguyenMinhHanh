---
title: "Delete Endpoint"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 5.8.1. </b> "
---

The SageMaker Endpoint continuously runs an inference instance, making it the primary source of AWS charges in this workshop.

Deleting the endpoint immediately stops compute resources and prevents further costs.

## Step 1

Navigate to

```
Inference

→ Endpoints
```

Select

```
scada-xgboost-endpoint
```

> **Figure 1**

>![Figure 1](/images/5-Workshop/5.10/delete-endpoint/endpoints.png)

---

## Step 2

Click

```
Delete
```

Confirm the deletion.

> **Figure 2**

>![Figure 1](/images/5-Workshop/5.10/delete-endpoint/endpoints.png)

---

Wait until the endpoint disappears from the endpoint list.