# Khai báo dùng AI — Nguyễn Đức Anh

| # | Công cụ | Bạn hỏi gì (tóm tắt) | Bạn dùng kết quả thế nào | Bạn có kiểm lại không? Bằng gì? |
|---|---|---|---|---|
| 1 | Codex | Hỏi cách hiểu thuộc tính/label; nhờ hỗ trợ soạn nháp danh sách lớp, IR log và tự đánh giá từ guideline, export và kết luận review do mình cung cấp | Dùng giải thích cho E5; tạo bản nháp E4 và tự đánh giá dựa trên quyết định review của mình; không dùng AI để xem ảnh hoặc tự gán nhãn | Có: đối chiếu `GUIDE.md`, `RULES.md`, dữ liệu export và kết quả `cabin_check` |
| 2 | `cabin_check.py` (script của lab, không phải AI) | Kiểm tra export và tạo diff với file bạn review chéo | Dùng báo cáo để tìm lỗi cấu trúc và các khác biệt cần tự xem trên CVAT | Có: kiểm tra kết quả script; verdict cuối cần đối chiếu ảnh/guideline |
