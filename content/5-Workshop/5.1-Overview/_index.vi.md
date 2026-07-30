---
title : "Giới thiệu"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---


## Giới thiệu

Trong bối cảnh các hệ thống công nghiệp hiện đại ngày càng được tự động hóa, các hệ thống **SCADA (Supervisory Control and Data Acquisition)** liên tục thu thập và truyền về một lượng lớn dữ liệu từ các cảm biến như nhiệt độ, áp suất, độ rung, lưu lượng hay tốc độ hoạt động của thiết bị. Những dữ liệu này phản ánh trạng thái vận hành của hệ thống theo thời gian thực và đóng vai trò quan trọng trong việc giám sát cũng như phát hiện các dấu hiệu bất thường trước khi xảy ra sự cố.

Tuy nhiên, việc theo dõi hàng triệu bản ghi dữ liệu và phát hiện lỗi theo phương pháp thủ công gần như không khả thi. Các phương pháp giám sát truyền thống chủ yếu dựa trên các ngưỡng cảnh báo được thiết lập trước hoặc kinh nghiệm của kỹ sư vận hành, dẫn đến khả năng phát hiện chậm, khó mở rộng và không tận dụng được hết giá trị của dữ liệu thu thập được. Vì vậy, việc ứng dụng **Machine Learning** để xây dựng hệ thống dự đoán lỗi (Fault Prediction) là một giải pháp hiệu quả, giúp doanh nghiệp chủ động phát hiện các dấu hiệu bất thường và thực hiện **Predictive Maintenance (Bảo trì dự đoán)** trước khi thiết bị gặp sự cố.

Đề tài **SCADA Fault Prediction Platform** được xây dựng nhằm phát triển một nền tảng dự đoán lỗi thiết bị công nghiệp dựa trên dữ liệu cảm biến SCADA, đồng thời tận dụng các dịch vụ Machine Learning trên nền tảng AWS để xây dựng một quy trình **MLOps** hoàn chỉnh. Hệ thống không chỉ tập trung vào việc huấn luyện mô hình mà còn mô phỏng toàn bộ vòng đời của một ứng dụng Machine Learning trong môi trường thực tế, từ lưu trữ dữ liệu, xử lý dữ liệu, huấn luyện mô hình, triển khai dịch vụ dự đoán cho đến giám sát và vận hành sau khi triển khai.

Trong đề tài này, bộ dữ liệu **SKAB (Skoltech Anomaly Benchmark)** được sử dụng làm nguồn dữ liệu đầu vào. Đây là bộ dữ liệu công khai mô phỏng các cảm biến trong hệ thống SCADA, bao gồm cả dữ liệu hoạt động bình thường và dữ liệu xảy ra lỗi. Bộ dữ liệu sẽ được lưu trữ trên **Amazon S3**, đóng vai trò là nơi lưu trữ tập trung cho toàn bộ dữ liệu và mô hình của hệ thống.

Sau khi dữ liệu được tải lên Amazon S3, **Amazon SageMaker Processing Job** sẽ thực hiện quá trình tiền xử lý (Data Preprocessing), bao gồm làm sạch dữ liệu, xử lý các giá trị thiếu, chuẩn hóa dữ liệu và xây dựng các đặc trưng (Feature Engineering) phục vụ cho việc huấn luyện mô hình. Tiếp theo, **Amazon SageMaker Training Job** sẽ sử dụng dữ liệu đã xử lý để huấn luyện mô hình **XGBoost**, đồng thời lưu kết quả và mô hình đã huấn luyện trở lại Amazon S3.

Khi quá trình huấn luyện hoàn tất, mô hình sẽ được triển khai dưới dạng **Amazon SageMaker Endpoint**. Endpoint đóng vai trò như một dịch vụ dự đoán trực tuyến (Real-time Inference Service), cho phép các ứng dụng hoặc người dùng gửi dữ liệu cảm biến thông qua API và nhận kết quả dự đoán ngay lập tức. Điều này giúp hệ thống có thể tích hợp với các ứng dụng SCADA hoặc Dashboard giám sát trong thực tế.

Để đảm bảo hệ thống luôn hoạt động ổn định sau khi triển khai, **Amazon CloudWatch** sẽ được sử dụng để theo dõi các chỉ số quan trọng của Endpoint như số lượng yêu cầu (Invocations), thời gian phản hồi (Latency), mức sử dụng CPU, bộ nhớ và tỷ lệ lỗi. Khi phát hiện Endpoint hoạt động bất thường hoặc vượt quá các ngưỡng được cấu hình, **Amazon SNS (Simple Notification Service)** sẽ tự động gửi email cảnh báo đến người quản trị, giúp xử lý sự cố kịp thời và đảm bảo tính sẵn sàng của hệ thống.



Đề tài được chia thành nhiều phần tương ứng với từng giai đoạn trong vòng đời của hệ thống Machine Learning. Trong đó, tôi phụ trách phần triển khai và vận hành mô hình sau khi dữ liệu đã được xử lý. Đây là giai đoạn quan trọng nhằm đưa mô hình Machine Learning vào môi trường thực tế để phục vụ quá trình dự đoán và giám sát.

Cụ thể, phần công việc của toi bao gồm:

- Huấn luyện mô hình **XGBoost** bằng **Amazon SageMaker Training Job**.
- Theo dõi tiến trình huấn luyện và kiểm tra kết quả trên **Amazon CloudWatch Logs**.
- Tạo **Amazon SageMaker Model** từ mô hình đã được huấn luyện.
- Cấu hình **Endpoint Configuration** và triển khai **SageMaker Endpoint** phục vụ dự đoán theo thời gian thực.
- Kiểm thử Endpoint thông qua **AWS Console** và **SageMaker Runtime API** để đánh giá khả năng dự đoán của mô hình.
- Theo dõi hiệu năng của Endpoint bằng **Amazon CloudWatch Metrics** và **CloudWatch Logs**, bao gồm các chỉ số như số lượng yêu cầu, thời gian phản hồi, CPU Utilization, Memory Utilization và tỷ lệ lỗi.
- Thiết lập **CloudWatch Alarm** để tự động phát hiện các tình huống bất thường như độ trễ cao hoặc Endpoint phát sinh lỗi.
- Cấu hình **Amazon SNS** để gửi email thông báo mỗi khi CloudWatch Alarm được kích hoạt, giúp người quản trị nhanh chóng phát hiện và xử lý sự cố.
- Dọn dẹp toàn bộ tài nguyên AWS sau khi hoàn thành workshop nhằm tránh phát sinh chi phí không cần thiết.

Thông qua phần workshop này, người thực hiện sẽ từng bước triển khai toàn bộ quy trình vận hành của một mô hình Machine Learning trên AWS, từ quá trình huấn luyện, triển khai dịch vụ dự đoán, kiểm thử Endpoint, giám sát hiệu năng đến cấu hình hệ thống cảnh báo tự động. Đây cũng là quy trình triển khai phổ biến trong các dự án Machine Learning thực tế trên nền tảng AWS.

Sau khi hoàn thành workshop, người học sẽ hiểu rõ cách sử dụng các dịch vụ **Amazon SageMaker**, **Amazon CloudWatch** và **Amazon SNS** để xây dựng một hệ thống dự đoán lỗi thiết bị công nghiệp có khả năng mở rộng, dễ quản lý và sẵn sàng triển khai trong môi trường sản xuất.