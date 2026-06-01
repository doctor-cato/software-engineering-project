## 1. Product Feature Identification (Xác định tính năng sản phẩm)

**Gom nhóm User Stories thành Tính năng (Epic/Feature):**

| Tính năng cốt lõi (Feature) | Giải quyết cho User Story nào? |
| :--- | :--- |
| **Giao diện rạp phim điện ảnh (Cinematic UI & Movie Browse)** | **US1** (Khách muốn xem danh sách phim đang/sắp chiếu và thông tin chi tiết phim để lựa chọn suất chiếu phù hợp) |
| **Khóa ghế thời gian thực (Realtime Seat Locking via Socket.io)** | **US2** (Khách muốn thấy sơ đồ ghế ngồi trực quan và trạng thái ghế đang được chọn theo thời gian thực để tránh đặt trùng ghế) |
| **Quy trình Checkout & Đặt trước bắp nước (Checkout Flow & Snack Booking)** | **US3** (Thành viên muốn chọn combo bắp nước đi kèm và tiến hành thanh toán nhanh chóng) |
| **Tích hợp cổng thanh toán trực tuyến (Payment Gateway Integration)** | **US4** (Thành viên muốn thanh toán qua ví điện tử MoMo/VNPAY hoặc thẻ ngân hàng an toàn, tiện lợi) |
| **Vé điện tử mã QR (QR Ticket Generator & History)** | **US5** (Thành viên muốn nhận vé điện tử có mã QR để quét check-in trực tiếp tại rạp không cần xếp hàng chờ in vé giấy) |
| **Bảng điều khiển quản trị (Admin Dashboard & Showtimes Management)** | **US6** (Admin muốn quản lý danh sách phim, phòng chiếu, suất chiếu và theo dõi doanh thu trực quan bằng biểu đồ) |
| **Đánh giá & Bình luận phim (Movie Review & Rating System)** | **US7** (Thành viên muốn để lại đánh giá sao và bình luận nhận xét về bộ phim sau khi đã xem xong) |

---

## 2. Product Backlog (Danh sách công việc của sản phẩm)

**Product Backlog của 3HD2Kcinema (Phiên bản sơ khai nhất):**

| Ưu tiên | Hạng mục (Item) | Vai trò (Persona) | Trạng thái |
| :--- | :--- | :--- | :--- |
| **1 (Cao nhất)** | **Trang chủ & Danh sách phim**<br>(Hiển thị banner nổi bật, danh sách phim Đang chiếu / Sắp chiếu) | Khách vãng lai & Thành viên | Đang làm (In Progress) |
| **2 (Cao)** | **Trang chi tiết phim & Lịch chiếu**<br>(Xem trailer, đạo diễn, diễn viên, thời lượng, lịch chiếu theo rạp) | Khách vãng lai & Thành viên | Đang làm (In Progress) |
| **3 (Cao)** | **Sơ đồ phòng chiếu & Chọn ghế**<br>(Hiển thị sơ đồ ghế ngồi trực quan phân loại ghế Thường, VIP, Đôi) | Thành viên | Cần làm (To-do) |
| **4 (Cao)** | **Đồng bộ khóa ghế thời gian thực**<br>(Tích hợp Socket.io hiển thị ghế người khác đang chọn và giữ ghế tạm thời trong 5 phút) | Thành viên | Cần làm (To-do) |
| **5 (Trung bình)** | **Đăng ký / Đăng nhập (JWT)**<br>(Xác thực tài khoản thành viên để lưu lịch sử giao dịch và tích điểm) | Khách vãng lai | Đang làm (In Progress) |
| **6 (Trung bình)** | **Đặt bắp nước & Trang Checkout**<br>(Chọn combo bắp nước đi kèm và xác nhận thông tin vé đặt) | Thành viên | Cần làm (To-do) |
| **7 (Trung bình)** | **Tích hợp thanh toán trực tuyến**<br>(Thanh toán thông qua cổng giả lập hoặc tích hợp ví điện tử MoMo/VNPAY) | Thành viên | Chờ xử lý (Pending) |
| **8 (Thấp)** | **Xuất vé điện tử QR Code**<br>(Tạo mã QR chứa thông tin vé sau khi thanh toán thành công để check-in tại quầy) | Thành viên | Chờ xử lý (Pending) |
| **9 (Thấp)** | **Trang Admin Dashboard**<br>(Giao diện quản lý phim, rạp, suất chiếu, combo bắp nước và doanh thu) | Admin | Chờ xử lý (Pending) |
| **10 (Thấp)** | **Đánh giá & Bình luận phim**<br>(Người dùng chấm điểm sao và viết review phim đã xem) | Thành viên | Ý tưởng (Backlog) |
| **11 (Thấp)** | **Gợi ý phim thông minh bằng AI**<br>(Hệ thống tự động đề xuất phim dựa trên sở thích và lịch sử xem của người dùng) | Thành viên | Ý tưởng (Backlog) |
