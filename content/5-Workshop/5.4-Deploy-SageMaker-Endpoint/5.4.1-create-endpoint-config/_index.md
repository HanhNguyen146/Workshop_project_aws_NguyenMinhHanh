---
title: "Deploy the Model to a SageMaker Endpoint"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 5.4.1. </b> "
---

After the training process is completed, the trained model is stored in Amazon S3. In this step, you will deploy the model to an Amazon SageMaker Endpoint using a Python script.

The deployment script automatically performs the following tasks:

- Create a SageMaker Model
- Create an Endpoint Configuration
- Create a SageMaker Endpoint



---

## Step 1

Open the deployment script in Visual Studio Code.

For example:

```text
deploy.py
```

```python
import boto3
import sagemaker
from sagemaker.sklearn.model import SKLearnModel

ROLE = 'arn:aws:iam::036071344072:role/SageMakerExecutionRole-MLOps'
REGION = 'ap-southeast-1'
ENDPOINT_NAME = 'scada-fault-predictor-v1'

MODEL_ARTIFACT = 's3://sagemaker-ap-southeast-1-036071344072/wind-turbine-gmm-2026-07-14-09-33-10-227/output/model.tar.gz'

def deploy_model():
    session = sagemaker.Session()
    model = SKLearnModel(
        model_data=MODEL_ARTIFACT,
        role=ROLE,
        entry_point='src/train.py',
        framework_version='1.2-1',
        sagemaker_session=session
    )
    predictor = model.deploy(
        initial_instance_count=1,
        instance_type='ml.t2.medium',
        endpoint_name=ENDPOINT_NAME
    )
    print(f"Endpoint deployed: {ENDPOINT_NAME}")
    return predictor


def delete_endpoint():
    sm = boto3.client('sagemaker', region_name=REGION)
    sm.delete_endpoint(EndpointName=ENDPOINT_NAME)
    print(f"Endpoint deleted: {ENDPOINT_NAME}")


def delete_endpoint_config():
    sm = boto3.client('sagemaker', region_name=REGION)
    sm.delete_endpoint_config(EndpointConfigName=ENDPOINT_NAME)
    print(f"EndpointConfig deleted: {ENDPOINT_NAME}")


if __name__ == '__main__':
    deploy_model()
```

---

## Step 2

Update the deployment parameters.

```python
ROLE = "arn:aws:iam::036071344072:role/SageMakerExecutionRole-MLOps"

REGION = "ap-southeast-1"

MODEL_NAME = "scada-xgboost-model"

ENDPOINT_NAME = "scada-fault-predictor-v1"

MODEL_ARTIFACT = "s3://sagemaker-ap-southeast-1-036071344072/wind-turbine-gmm-2026-07-14-09-33-10-227/output/model.tar.gz"
```

Where:

- **ROLE** is the IAM role used by SageMaker.
- **REGION** is the AWS Region where the resources are deployed.
- **MODEL_NAME** is the name of the SageMaker model.
- **ENDPOINT_NAME** is the name of the endpoint to be created.
- **MODEL_ARTIFACT** is the Amazon S3 path to the trained model artifact.

---

## Step 3

Open a terminal and run the following command:

```bash
python aws/deploy.py
```

The script will automatically:

- Create a SageMaker Model
- Create an Endpoint Configuration
- Create a SageMaker Endpoint

The deployment uses:

- **Instance type:** `ml.t2.medium`
- **Instance count:** `1`

When the deployment is completed successfully, the terminal displays:

```text
Endpoint deployed: scada-fault-predictor-v1
```

---

## Step 4

Verify the endpoint in the AWS Management Console.

Navigate to:

```text
Inference

→ Endpoints
```

Confirm that the following endpoint:

```text
scada-fault-predictor-v1
```

is in the **InService** state.

> **Figure 4**

> ![Figure 4](/images/5-Workshop/5.6/deploy-model/endpoint-inservice.png)

---

Once the endpoint reaches the **InService** state, the deployed model is ready to receive inference requests.