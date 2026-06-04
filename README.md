\# Nhận diện Cảm xúc Khuôn mặt trên Thiết bị Nhúng (FER - TinyML)



\## 1. Thông tin Đề tài

\- \*\*Môn học:\*\* Mạng Cảm Biến

\- \*\*Sinh viên thực hiện:\*\* Lý Việt Linh

\- \*\*Mô tả:\*\* Dự án ứng dụng Trí tuệ nhân tạo nhúng (TinyML) để phân loại 4 trạng thái cảm xúc (Buồn, Ngạc nhiên, Trung tính, Vui). Mô hình sử dụng kiến trúc MobileNetV2 96x96 0.35, ảnh đầu vào Grayscale để giảm dung lượng và tránh thiên kiến (Bias), lượng tử hóa Int8 để tối ưu tài nguyên.

\- \*\*Hiệu năng:\*\* Accuracy 97.56% (Test Set), Inference Time 224ms.



\## 2. Cấu trúc Thư mục

\- `edge-impulse-sdk/`: Thư viện lõi SDK của Edge Impulse.

\- `model-parameters/`: Chứa các trọng số (weights) của mạng MobileNetV2 đã được lượng tử hóa (Int8).

\- `tflite-model/`: Chứa mã nguồn EON Compiler đã dịch đồ thị tính toán thành C++ tĩnh.



\## 3. Hướng dẫn cài đặt và chạy

1\. Clone repository này về máy:

&#x20;  `git clone https://github.com/LinhViet130905/mangcambien-cuoiky-lyvietlinh.git`

2\. Include thư viện vào dự án vi điều khiển của bạn: Thêm `#include "edge-impulse-sdk/classifier/ei\_run\_classifier.h"`

3\. Truyền mảng dữ liệu (Raw Features) chứa giá trị các điểm ảnh (0.0 - 1.0) vào hàm `run\_classifier()` để nhận về vector xác suất phân loại.

