---
title: "Worklog Week 4"
date: 2026-06-22
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu:

* Upgrade preprocessing pipeline to run on AWS cloud.
* Configure AWS SageMaker Processing Job for large data volumes.

### Các công việc cần triển khai trong tuần này:

| Thứ / Day | Công việc / Task | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| Mon | - Read documentation on Amazon SageMaker Processing Job. | 22/06/2026 | 24/06/2026 |  |
| Tue | - Write script `aws/run_processing_job.py` to push `src/preprocessing.py` to AWS. | 23/06/2026 | 24/06/2026 |  |
| Wed | - Configure IAM Role and S3 Bucket for Processing Job. | 24/06/2026 | 25/06/2026 |  |
| Thu | - Integrate Scikit-Learn library into SageMaker Processing container. | 25/06/2026 | 26/06/2026 |  |
| Fri | - **Practice:** Trigger Processing Job and verify clean data on S3. | 26/06/2026 | 26/06/2026 |  |

### Kết quả đạt được:

* Successfully migrated preprocessing to cloud environment using SageMaker Processing Job.
* Clean data is automatically stored on Amazon S3 ready for training.
