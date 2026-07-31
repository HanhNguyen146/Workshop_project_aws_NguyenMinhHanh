---
title: "Worklog Week 5"
date: 2026-06-29
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu:

* Advanced Feature Engineering.
* Create new features from SCADA data to enhance the power of the fault prediction model.

### Các công việc cần triển khai trong tuần này:

| Thứ / Day | Công việc / Task | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| Mon | - Research lag feature creation for SCADA time-series data. | 29/06/2026 | 29/06/2026 | |
| Tue | - Add `rolling_mean`, `rolling_std` feature generation to `src/preprocessing.py`. | 30/06/2026 | 30/06/2026 | |
| Wed | - Handle angular features (e.g., turbine angle) using trigonometric transformations (sin/cos). | 01/07/2026 | 01/07/2026 | |
| Thu | - Perform Data Scaling/Normalization using `StandardScaler`. | 02/07/2026 | 02/07/2026 | |
| Fri | - **Practice:** Re-validate dataset quality after adding new features using `data_validation.py`. | 03/07/2026 | 03/07/2026 | |

### Kết quả đạt được:

* Improved input data quality with advanced Feature Engineering techniques.
* SCADA dataset enriched with useful time-series information.
