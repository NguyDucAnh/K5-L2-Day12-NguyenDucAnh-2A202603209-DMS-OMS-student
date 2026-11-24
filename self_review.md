# Tự đánh giá — Nguyễn Đức Anh · G10

## 1. Tự rà soát 4 cảnh

Các trường hợp dưới đây được chọn từ review chéo. Theo kết luận của Nguyễn Đức Anh, các phương án của hai người đều chấp nhận được theo guideline; không sửa nhãn.

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| S01_ir | face.eye_left | ok | Khác mức độ tự tin: mine `unknown`, peer `open`; cả hai cách diễn giải được chấp nhận sau khi xem ảnh. | Không |
| S04_ir | face.glasses | ok | Mine `unknown`, peer `none`; ghi nhận ngưỡng nhận biết kính khác nhau. | Không |
| D03 | face.eye_left | ok | Mine `open`, peer `unknown`; cả hai cách gán được chấp nhận sau khi xem ảnh. | Không |
| D05 | face.eye_left | ok | Mine `closed`, peer `unknown`; khác biệt ở ngưỡng xác định mí khép. | Không |

## 2. Khác biệt lặp lại và cách tránh

Khác biệt lặp lại: một người chọn giá trị cụ thể, người kia chọn `unknown` hoặc `other` cho cùng trường. Qua review, mình ghi nhận cả hai cách có thể hợp lý tùy mức độ nhìn rõ.

Lần sau, mình sẽ đối chiếu định nghĩa `unknown`/`other` trong guideline và trao đổi trước về ngưỡng quan sát, đồng thời giữ lại lý do cho các trường hợp khó.

## 3. Bài học từ disagreement log

Một ví dụ là `D03.png`, trường `face.eye_left`: mine `open`, peer `unknown`. Review giúp mình nhớ rằng nhãn trạng thái mắt mô tả điều nhìn thấy trong khung hình; nếu khe mắt không rõ thì `unknown` cũng là lựa chọn phù hợp.
