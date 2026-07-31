---
title: "Worklog Tuần 5"
date: 2026-06-29
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu:

* Khai phá đặc trưng nâng cao (Advanced Feature Engineering).
* Tạo các đặc trưng mới từ dữ liệu SCADA để tăng sức mạnh cho mô hình dự đoán lỗi.

### Các công việc cần triển khai trong tuần này:

| Thứ / Day | Công việc / Task | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Nghiên cứu phương pháp tạo lag features cho dữ liệu chuỗi thời gian SCADA. | 29/06/2026 | 29/06/2026 | |
| 3 | - Bổ sung hàm tạo đặc trưng `rolling_mean`, `rolling_std` vào `src/preprocessing.py`. | 30/06/2026 | 30/06/2026 | |
| 4 | - Xử lý đặc trưng góc (ví dụ: góc quay tuabin) bằng phép biến đổi lượng giác (sin/cos). | 01/07/2026 | 01/07/2026 | |
| 5 | - Thực hiện Scaling/Normalization dữ liệu bằng `StandardScaler`. | 02/07/2026 | 02/07/2026 | |
| 6 | - **Thực hành:** Xác thực lại chất lượng của tập dữ liệu sau khi thêm tính năng mới thông qua `data_validation.py`. | 03/07/2026 | 03/07/2026 | |

### Kết quả đạt được:

* Cải thiện chất lượng dữ liệu đầu vào với các kỹ thuật Feature Engineering tiên tiến.
* Bộ dữ liệu SCADA có thêm nhiều thông tin hữu ích về chuỗi thời gian.
