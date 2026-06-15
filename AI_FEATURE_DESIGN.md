# AI Feature Design

## Feature name
AI Sentiment Analysis for Movie Reviews (AI Phân tích Cảm xúc Đánh giá phim)

## User value
Giúp người dùng (khán giả) nhanh chóng nắm bắt chất lượng thực sự của một bộ phim thông qua tóm tắt điểm mạnh, điểm yếu từ hàng ngàn bình luận, thay vì phải tốn thời gian đọc thủ công từng đánh giá.

## Input
Một danh sách các bình luận đánh giá (reviews) ẩn danh của khán giả về một bộ phim cụ thể (được lấy từ collection `Reviews` trong MongoDB).

## Output
- Tóm tắt tổng quan cảm xúc (Ví dụ: 85% Tích cực, 15% Tiêu cực).
- Top những điểm khán giả khen ngợi nhiều nhất (recurring positive points).
- Top những điểm khán giả chê nhiều nhất (recurring negative issues).

## Human control
Quản trị viên có quyền xem xét, chỉnh sửa hoặc ẩn đi kết quả tóm tắt của AI nếu phát hiện thông tin không chính xác. Người dùng cuối có thể nhấn xem bình luận gốc (Original comments) để đối chiếu trực tiếp với kết quả tóm tắt của AI.

## Risks
- **Hallucinated summary:** AI bịa đặt thông tin không có trong bình luận gốc (ví dụ: khen kỹ xảo dù không ai nhắc tới).
- **Sensitive information:** Có thể có thông tin cá nhân vô tình lọt vào trong nội dung bình luận của người dùng và gửi đi cho AI Provider.
- **Over-trust in AI output:** Khán giả hoàn toàn tin tưởng vào tóm tắt của AI dẫn đến bỏ lỡ những bộ phim hay nhưng bị AI đánh giá sai lệch.

## Mitigation
- Hiển thị danh sách các bình luận gốc ngay bên dưới phần tóm tắt để người dùng tự kiểm chứng.
- Đánh dấu rõ ràng trên giao diện UI dòng chữ: *"Đây là tóm tắt tự động bởi AI, có thể chứa sai sót"*.
- Làm sạch (sanitize) dữ liệu đầu vào: Chỉ gửi nội dung bình luận (comment text) cho AI, **tuyệt đối không** gửi tên người dùng (User ID, Name) hoặc thông tin cá nhân.
