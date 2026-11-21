# Tự đánh giá — Dương Quốc Anh · G01

**MSSV:** 2A202603286

## 1. Tự rà soát 4 khung

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| S02_ir | Ghế phía trái ảnh | `wrong_class` | Bản đầu gán `child_seat`. Dũng chỉ ra quai xách và dáng vỏ ngả của nôi. Bản v2 dùng `infant_seat`, `seat=rear_right`, `facing=front`. | Có |
| S08_ir | Ghế giữa hàng sau | `seat_flip` | Bản đầu ghi `rear_left` cho cả box giữa và box ngoài bên phải ảnh. Em sửa box giữa thành `rear_middle`. | Có |
| D02 | Khóe miệng phải và hai điểm giữa môi | `flag` | Chai che vùng miệng. Bản v2 đặt `outside` cho `mouth_right`, `lip_upper` và `lip_lower` vì chưa định vị chắc ba điểm. | Có |
| D05 | Hai bàn tay tài xế | `lr_flip` | Bản đầu ghi cả hai tay là `left`. Bản v2 đổi tay gần điện thoại thành `right`. | Có |

## 2. Lỗi em lặp lại nhiều nhất

**Lỗi:** Gán sai vị trí ghế trong phần OMS. Ở S03 RGB/IR, vật ở giữa hàng ghế sau từng bị gán `seat=driver`. Ở S08_ir, em gán nhầm box giữa thành `rear_left`.

**Vì sao:** Em chưa xác định vị trí theo xe trước khi chọn thuộc tính. Camera nhìn về phía sau nên bên trái ảnh là bên phải xe.

**Cách tránh:** Với mỗi khung OMS, em sẽ xác định ba vị trí ghế sau trước khi vẽ box. Sau khi gán, em rà lại mọi giá trị `seat` và so vị trí của các box trong cặp RGB/IR cùng cảnh.

## 3. Ghi chú về chấm chéo

Ở S02, Hà Huy Dũng nhận ra đó là nôi xách, còn bản đầu của em dùng `child_seat`. Em rút ra rằng cần nhìn quai xách và dáng vỏ trước khi chọn lớp. Khi đã xác định là `infant_seat`, em kiểm hướng lắp để điền `facing`.

Bản v2 đã được kiểm trên 22 khung theo bộ nhãn hiện hành và báo 0 lỗi, 0 cảnh báo. Khi rà lại ảnh, em vẫn cần kiểm mép box tay ở D02/D03 và xác nhận các điểm `face13` ở D03.
