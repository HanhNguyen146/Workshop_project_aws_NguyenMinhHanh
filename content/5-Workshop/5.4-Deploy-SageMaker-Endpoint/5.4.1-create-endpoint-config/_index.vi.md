---
title: "Triển khai mô hình lên SageMaker Endpoint"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 5.4.1. </b> "
---

Sau khi quá trình huấn luyện hoàn tất, mô hình được lưu trong Amazon S3. Trong bước này, bạn sẽ triển khai mô hình lên Amazon SageMaker Endpoint bằng tập lệnh Python.

Lệnh triển khai sẽ tự động thực hiện:

- Tạo SageMaker Model
- Tạo Endpoint Configuration
- Tạo SageMaker Endpoint


---

## Bước 1

Mở file triển khai trong Visual Studio Code.

Ví dụ:

```text
deploy.py
```

```
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

## Bước 2

Cập nhật các tham số triển khai.

```python
ROLE = "arn:aws:iam::036071344072:role/SageMakerExecutionRole-MLOps"

REGION = "ap-southeast-1"

MODEL_NAME = "scada-xgboost-model"

ENDPOINT_NAME = "scada-fault-predictor-v1"

MODEL_ARTIFACT = "s3://sagemaker-ap-southeast-1-036071344072/wind-turbine-gmm-2026-07-14-09-33-10-227/output/model.tar.gz"
```

Trong đó:

- **ROLE** là IAM Role được SageMaker sử dụng.
- **REGION** là vùng AWS triển khai.
- **MODEL_NAME** là tên mô hình trên SageMaker.
- **ENDPOINT_NAME** là tên Endpoint sẽ được tạo.
- **MODEL_ARTIFACT** là đường dẫn đến mô hình đã huấn luyện trên Amazon S3.


---

## Bước 3

Mở Terminal và chạy lệnh:

```bash
python aws/deploy.py
```

Chương trình sẽ tự động:

- Tạo SageMaker Model
- Tạo Endpoint Configuration
- Tạo SageMaker Endpoint

Quá trình triển khai sử dụng:

- **Instance type:** `ml.t2.medium`
- **Instance count:** `1`

Khi hoàn tất, Terminal sẽ hiển thị:

```text
Endpoint deployed: scada-fault-predictor-v1
```


## Bước 4

Kiểm tra Endpoint trên AWS Console.

Điều hướng đến:

```text
Inference

→ Endpoints
```

Xác nhận Endpoint:

```text
scada-fault-predictor-v1
```

đang ở trạng thái **InService**.

> **Hình 4**

>![Figure 1](/images/5-Workshop/5.6/deploy-model/endpoint-inservice.png)

---

Sau khi Endpoint ở trạng thái **InService**, mô hình đã sẵn sàng để nhận các yêu cầu dự đoán (Inference).