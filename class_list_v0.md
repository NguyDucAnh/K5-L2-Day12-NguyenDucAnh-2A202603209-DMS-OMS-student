# Danh sách lớp v0 — Nguyễn Đức Anh · G10

Danh sách nháp theo chức năng DMS/OMS và Guideline Cabin v1.0. Khả năng quan sát IR dưới đây nói về đặc điểm hình ảnh, không thay cho việc kiểm tra từng khung cụ thể.

## DMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng DMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | `person` / `seat` | driver | Xác định người lái và liên kết các quan sát với đúng người | Thường thấy được hình dáng/vị trí người; độ rõ tùy ánh sáng và che khuất |
| 2 | `face` / `eye_left`, `eye_right` | open / closed / unknown | Theo dõi trạng thái mắt, hỗ trợ phát hiện nhắm mắt hoặc mệt mỏi | Có thể thấy; phản xạ kính, bóng tối hoặc góc mặt có thể làm trạng thái thành unknown |
| 3 | `face` / `gaze_zone` | road, mirror_*, cluster, center, lap, other | Ước lượng tài xế đang chú ý đường hay nhìn sang vùng khác | Hướng đầu thường hỗ trợ; hướng mắt có thể khó thấy qua kính hoặc khi mặt quay |
| 4 | `face` / `glasses` | none / clear / sun / unknown | Diễn giải độ tin cậy của quan sát mắt và xử lý trường hợp kính che mắt | Khung kính có thể thấy; loại tròng có thể không phân biệt được trên NIR |
| 5 | `face13` / 13 điểm mặt | tọa độ điểm, cờ occluded/outside | Định vị mắt, mũi, miệng để phân tích tư thế và biểu cảm | Điểm thấy được khi mặt đủ lớn; vùng che khuất hoặc ngoài khung phải đánh cờ |
| 6 | `hand` / `whose`, `side`, `on_wheel` | driver/passenger; left/right; yes/no/unknown | Theo dõi tay tài xế và tương tác với vô lăng | Hình dáng và vị trí tay thường thấy; vật che hoặc vùng tối làm giảm độ chắc chắn |
| 7 | `phone` / `state` | held / mounted / lap | Phát hiện sử dụng điện thoại gây xao nhãng | Có thể thấy đường viền/vị trí; chỉ gán khi nhận ra hình dạng điện thoại |
| 8 | `person` / `seatbelt` | worn_correct / worn_incorrect / not_worn / unknown | Kiểm tra việc sử dụng dây an toàn | Dây có thể khó tách khỏi quần áo trên IR; không rõ thì unknown |

## OMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng OMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | `person` / `seat` | driver, front_passenger, rear_* | Đếm và xác định vị trí người ngồi trong xe | Người thường nhận ra qua hình dáng/vị trí; ảnh SVIRO là IR mô phỏng |
| 2 | `person` / `seatbelt` | worn_correct / worn_incorrect / not_worn / unknown | Bổ sung thông tin an toàn của người ngồi | Độ rõ phụ thuộc tương phản dây với áo; ảnh tối cần unknown |
| 3 | `face` | box khuôn mặt | Xác định sự hiện diện của mặt người lớn trong vùng ghế | Có thể thấy hình dạng mặt; OMS chỉ yêu cầu box, không cần thuộc tính mặt |
| 4 | `child_seat` / `occupied` | no / unknown | Nhận diện ghế trẻ em và biết có thể xác nhận ghế trống không | Hình dáng ghế thường còn nhận ra; bên trong có thể không rõ |
| 5 | `infant_seat` / `facing` | rear / front | Nhận diện nôi và hướng lắp để hỗ trợ kiểm tra an toàn | Đường nét/hướng nôi có thể thấy; không suy đoán nếu ảnh không đủ rõ |
| 6 | `object` / `type` | bag / box / cup / other | Nhận diện đồ vật bị bỏ quên hoặc cần lưu ý trong cabin | Hình dáng thường còn thấy; phân loại nhỏ/khó rõ nên dùng other |
| 7 | `frame_meta` / `modality` | rgb / ir | Ghi nhận loại cảm biến/ảnh để diễn giải quan sát phù hợp | Đây là metadata từ loại khung, không phải vật thể cần nhận diện |

## Câu hỏi leo thang

1. **Câu hỏi:** Khi một vật nằm trong ghế trẻ em nhưng ảnh IR không cho thấy rõ vật đó, có cần giữ box `object` với loại `other`, hay chỉ ghi box `child_seat` và `occupied = unknown`?
   - **Khung ví dụ:** `S03_ir.png` (điểm khác nhau về loại box giữa hai bản export; cần mở ảnh để xác nhận tình huống thực tế).
   - **Tạm gán:** Chỉ tạo box cho vật khi nhìn thấy hình dạng của vật; nếu không đủ bằng chứng thì không đoán.
2. **Câu hỏi:** Với ảnh IR, khi thấy tư thế đầu hướng xuống nhưng mắt bị phản xạ/che, `gaze_zone` nên là `lap` hay `other`?
   - **Khung ví dụ:** `D03.png` (hai bản export khác nhau ở `gaze_zone`; cần xem ảnh để xác nhận hướng nhìn).
   - **Tạm gán:** Chọn `lap` chỉ khi hướng mắt và đầu ủng hộ việc nhìn xuống đùi; nếu không chắc, dùng `other` theo guideline.
