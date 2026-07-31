---
title: "Worklog Tuần 3"
date: 2026-06-15
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Cấu trúc hóa mã nguồn tiền xử lý dữ liệu và kiểm thử dữ liệu (Data Validation).

* Chuyển đổi mã nguồn từ Jupyter Notebook sang script Python độc lập để tự động hóa quy trình làm sạch dữ liệu.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Tạo tệp `src/preprocessing.py`. <br> - Viết hàm `load_data()` và `handle_missing_values()` để đọc và xử lý dữ liệu SCADA thô. | 15/06/2026 | 15/06/2026 | <https://pandas.pydata.org/docs/> |
| 3   | - Lập trình module `src/data_validation.py` với hàm `validate_data()` để tự động hóa việc kiểm tra tính toàn vẹn của dữ liệu đầu vào. | 16/06/2026 | 16/06/2026 | <https://docs.python.org/3/> |
| 4   | - Viết kịch bản `data_validation.py` để chạy thử nghiệm kiểm thử độc lập mà không cần chạy toàn bộ pipeline. | 17/06/2026 | 17/06/2026 | <https://docs.pytest.org/> |
| 5   | - Tích hợp cơ chế nội suy (interpolate) nhằm xử lý chuỗi thời gian bị thiếu (time-series lag) và bảo toàn các giá trị ngoại lai (outliers) hợp lệ. | 18/06/2026 | 18/06/2026 | <https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.interpolate.html> |
| 6   | - **Thực hành:** <br>&emsp; + Chạy thử kịch bản `data_validation.py` cục bộ qua terminal. <br>&emsp; + Đảm bảo kết quả trả về trạng thái 'PASS' và xử lý mọi cảnh báo (warnings) trước khi xuất dữ liệu chuẩn (clean data). | 19/06/2026 | 19/06/2026 |  |

### Kết quả đạt được tuần 3:

* Đã chuyển đổi thành công quy trình làm sạch dữ liệu từ môi trường thử nghiệm (Notebook) sang script Python tiêu chuẩn (`src/preprocessing.py`).

* Xây dựng thành công hệ thống kiểm thử độc lập (`data_validation.py`) giúp phân tích báo cáo lỗi, đảm bảo dữ liệu luôn đạt tiêu chuẩn đầu vào cho các mô hình học máy.