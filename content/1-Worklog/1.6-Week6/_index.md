---
title: "Worklog Week 6"
date: 2026-07-06
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu:

* Finalize Data Validation Automation.
* Integrate early warning mechanisms when anomalies are detected in data streams.

### Các công việc cần triển khai trong tuần này:

| Thứ / Day | Công việc / Task | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| Mon | - Extend `validate_data()` module to check data distribution (Data Drift). | 06/07/2026 | 08/07/2026 |  |
| Tue | - Add exception checking rules: physical min/max limits of each sensor. | 07/07/2026 | 08/07/2026 |  |
| Wed | - Integrate Exception handling and clear Logging in `data_validation.py`. | 08/07/2026 | 09/07/2026 |  |
| Thu | - Generate testing reports in JSON/Text format. | 09/07/2026 | 10/07/2026 |  |
| Fri | - **Practice:** Test with intentionally corrupted data to ensure validation script correctly blocks bad data. | 10/07/2026 | 10/07/2026 |  |

### Kết quả đạt được:

* Finalized comprehensive automated data validation mechanism.
* Successfully prevented garbage data streams before machine learning ingestion.
