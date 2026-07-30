---
title: "Xem kết quả dự đoán"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 5.5.1. </b> "
---



Sau khi gửi yêu cầu thành công, Amazon SageMaker Endpoint sẽ trả về kết quả dự đoán từ mô hình XGBoost đã được triển khai.

Kết quả có thể bao gồm:

- Nhãn dự đoán
- Xác suất dự đoán
- Độ tin cậy của mô hình

## Ví dụ kiểm tra

```python
data1 = {
    "sensors": {
        "LV ActivePower (kW)_diff_1": 0.5,
        "Wind Speed (m/s)_diff_1": 0.1,
        "Theoretical_Power_Curve (KWh)_diff_1": 0.2
    },
    "timestamp": "2026-07-15T10:00:00"
}

data2 = {
    "sensors": {
        "LV ActivePower (kW)_diff_1": 50.0,
        "Wind Speed (m/s)_diff_1": 8.0,
        "Theoretical_Power_Curve (KWh)_diff_1": 45.0
    },
    "timestamp": "2026-07-15T10:00:00"
}
```
Kết quả trả về ở terminal và trên AWS Lambda:
> **Hình 1**

>![Figure 1](/images/5-Workshop/5.7/view-prediction/result.png)
>![Figure 1](/images/5-Workshop/5.7/view-prediction/result..png)
Dựa trên kết quả trả về, người dùng có thể xác định dữ liệu SCADA đang ở trạng thái bình thường hay có dấu hiệu bất thường để phục vụ cho bài toán bảo trì dự đoán.