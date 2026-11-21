# Danh sách lớp v0 — Dương Quốc Anh · G01

## DMS

| Lớp hoặc thuộc tính | Giá trị đề xuất | Dùng để làm gì | Quan sát trên NIR |
|---|---|---|---|
| `person` | `seat = driver` | Xác định người lái và liên kết mặt, tay, dây an toàn với người đó. | Nhìn được dáng người khi vẫn nằm trong vùng camera. |
| `face` | Hộp mặt | Cắt vùng cần theo dõi cho mắt, điểm mặt và hướng nhìn. | Hữu ích trong cabin thiếu sáng nếu mặt còn thấy rõ. |
| `eye_left`, `eye_right` | `open`, `closed`, `unknown` | Theo dõi trạng thái từng mắt theo thời gian để tính thời lượng nhắm mắt. | Phản xạ hoặc vật che có thể làm một mắt không phân biệt được. |
| `glasses` | `none`, `clear`, `sun`, `unknown` | Đánh giá khi nào tín hiệu mắt có thể kém tin cậy do kính. | Một số kính râm có thể trông trong suốt trên NIR. |
| `gaze_zone` | `road`, `mirror_l`, `mirror_r`, `mirror_c`, `cluster`, `center`, `lap`, `other` | Ước lượng thời lượng nhìn khỏi đường và phân biệt nhìn gương với nhìn xuống đùi. | Cần thấy đủ hướng mắt hoặc đầu. |
| `face13` | 13 điểm mặt với cờ `occluded` và `outside` | Theo dõi hình học mắt, mũi và miệng để hỗ trợ ước lượng hướng đầu và độ mở mắt. | Chất lượng tùy kích thước mặt, góc quay và phần bị che. |
| `hand` | `whose`, `side`, `on_wheel` | Xác định tay ai đang ở vô lăng và tay nào có thể đang cầm vật. | Cần thấy vùng tiếp xúc để xác định `on_wheel`. |
| `phone` | `held`, `mounted`, `lap` | Phân biệt điện thoại đang được cầm với điện thoại trên giá hoặc trên đùi. | Dựa vào cạnh, góc hoặc màn hình thấy được. |

## OMS

| Lớp hoặc thuộc tính | Giá trị đề xuất | Dùng để làm gì | Quan sát trên IR-sim |
|---|---|---|---|
| `person` | Hộp người và `seat` | Xác định ghế nào có người lớn để gắn cảnh báo đúng vị trí. | Dựa vào hình dáng và vị trí của phần cơ thể thấy được. |
| `face` | Hộp mặt | Liên kết vùng mặt thấy được với người ngồi để hỗ trợ theo dõi tư thế. | Có thể khó thấy khi mặt quay đi hoặc nằm trong vùng tối. |
| `seatbelt` | `worn_correct`, `worn_incorrect`, `not_worn`, `unknown` | Gắn nhắc dây an toàn với ghế có người. | Cần thấy đường dải dây. G01 SVIRO chỉ dùng `not_worn` hoặc `unknown`. |
| `child_seat` | Hộp vỏ ghế, `seat`, `occupied = yes / no / unknown` | Xác định ghế trẻ em và tình trạng có người ngồi tại từng vị trí. | Dựa vào vỏ và lòng ghế. Khi không thấy rõ ở IR-sim, giữ `unknown`. |
| `infant_seat` | Hộp, `seat`, `facing = rear / front` | Xác định vị trí và chiều lắp nôi để hỗ trợ cảnh báo lắp đặt. | Dựa vào kết cấu nhìn thấy và hướng của nôi so với xe. |
| `object` | Hộp, `seat`, `type = bag / box / cup / other` | Phân biệt hành lý với người và nhận ra vật đặt trong ghế trẻ em. | Hình dáng và vị trí còn hữu ích khi mất thông tin màu. |

## Câu hỏi leo thang

1. Ở S03 RGB/IR, khi vỏ ghế thấy rõ nhưng phần bên trong có hình người hoặc vật giả người, coach yêu cầu dấu hiệu nào để chốt occupied=yes theo schema mới? Bản v2 giữ thuộc tính trên hộp ghế.
2. Ở D03, khi cúi đầu vẫn thấy đủ mặt để vẽ box nhưng từng mép mí chưa xác định được, nên dùng outside cho điểm nào và căn cứ nào đủ để gán occluded? Bản v2 có box mặt và ghi ca face13 cần xác nhận.
