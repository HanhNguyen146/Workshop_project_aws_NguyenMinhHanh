---
title: "Worklog Tuần 4"
date: 2026-06-22
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu:

* Nâng cấp pipeline tiền xử lý để có thể chạy trên đám mây AWS.
* Cấu hình AWS SageMaker Processing Job cho khối lượng dữ liệu lớn.

### Các công việc cần triển khai trong tuần này:

| Thứ / Day | Công việc / Task | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Đọc tài liệu về Amazon SageMaker Processing Job. | 22/06/2026 | 24/06/2026 |  |
| 3 | - Viết script `aws/run_processing_job.py` để đẩy mã nguồn `src/preprocessing.py` lên AWS. | 23/06/2026 | 24/06/2026 |  |
| 4 | - Cấu hình IAM Role và S3 Bucket cho Processing Job. | 24/06/2026 | 25/06/2026 |  |
| 5 | - Tích hợp thư viện Scikit-Learn vào container của SageMaker Processing. | 25/06/2026 | 26/06/2026 |  |
| 6 | - **Thực hành:** Kích hoạt luồng chạy Processing Job và kiểm tra kết quả dữ liệu sạch trên S3. | 26/06/2026 | 26/06/2026 |  |

### Kết quả đạt được:

* Đưa thành công quá trình tiền xử lý lên môi trường đám mây bằng SageMaker Processing Job.
* Dữ liệu sạch được lưu trữ tự động trên Amazon S3 sẵn sàng cho huấn luyện.
