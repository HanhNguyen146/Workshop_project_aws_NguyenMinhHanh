---
title: "Worklog Tuần 6"
date: 2026-07-06
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu:

* Hoàn thiện Data Validation Automation.
* Tích hợp cơ chế cảnh báo sớm khi phát hiện bất thường trong luồng dữ liệu.

### Các công việc cần triển khai trong tuần này:

| Thứ / Day | Công việc / Task | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Mở rộng module `validate_data()` để kiểm tra phân phối dữ liệu (Data Drift). | 06/07/2026 | 08/07/2026 |  |
| 3 | - Bổ sung các rule kiểm tra ngoại lệ: giới hạn min/max vật lý của từng cảm biến. | 07/07/2026 | 08/07/2026 |  |
| 4 | - Tích hợp xử lý Exception và xuất Log rõ ràng trong `data_validation.py`. | 08/07/2026 | 09/07/2026 |  |
| 5 | - Tạo báo cáo kiểm thử định dạng JSON/Text. | 09/07/2026 | 10/07/2026 |  |
| 6 | - **Thực hành:** Kiểm thử luồng dữ liệu lỗi cố ý để đảm bảo validation script hoạt động chính xác chặn lại dữ liệu xấu. | 10/07/2026 | 10/07/2026 |  |

### Kết quả đạt được:

* Hoàn thiện cơ chế tự động kiểm thử dữ liệu chuyên sâu.
* Ngăn chặn thành công các luồng dữ liệu rác trước khi đưa vào mô hình học máy.
