# Khai báo dùng AI — Dương Quốc Anh

| Công cụ | Yêu cầu | Sử dụng kết quả | Kiểm tra |
|---|---|---|---|
| Codex | Hỗ trợ bài Day 12, mã G01, chuẩn bị trong thư mục bài và giữ local. | Chuẩn bị tệp, chọn đúng 22 khung cốt lõi, soạn danh sách lớp v0 và mẫu ghi nhận. | Đối chiếu GUIDE, SUBMISSION và RUBRIC. Việc chuyển tệp ảnh chỉ diễn ra trên máy. |


## Rà lại bản nháp G01 theo GUIDE v1.0

Codex chạy các lượt dò YuNet, MediaPipe, YOLOv7 và Qwen-VL cục bộ để rà box mặt, tay và vùng ghế còn mâu thuẫn. Bản v2 sửa vị trí và phân loại trên các khung có đủ tín hiệu, ghi các ca cần xác nhận trong draft_G01/review_draft_G01_v2.csv và giữ các thuộc tính chưa rõ ở unknown hoặc other theo schema. Bộ đọc của CVAT và cabin_check đã kiểm ZIP. Độ đúng của các nhãn vẫn cần đối chiếu trong CVAT.
