# 3HD2Kcinema - Product Backlog & Feature Identification

Tài liệu này tổng hợp danh sách các tính năng (Feature Identification) và Product Backlog cho dự án ứng dụng đặt vé xem phim trực tuyến 3HD2Kcinema, bao gồm cả các tính năng cốt lõi (MVP) và các tính năng mở rộng trong tương lai.

---

## 1. Feature Identification (Xác định tính năng)

Dựa trên tầm nhìn và mục tiêu của dự án, các tính năng được phân loại thành các nhóm chính (Epics) như sau:

### Epic 1: Giao diện người dùng & Trải nghiệm (UI/UX)
- **Giao diện hiện đại (Cinematic UI):** Dark theme, màu nhấn đỏ, hiệu ứng glow mờ ảo.
- **Trang chủ (Homepage):** Banner phim nổi bật, danh sách phim đang chiếu, sắp chiếu.
- **Trang chi tiết phim (Movie Detail):** Hiển thị trailer, thông tin phim (đạo diễn, diễn viên, thời lượng, độ tuổi), lịch chiếu và đánh giá.
- **Responsive Design:** Tối ưu hóa giao diện cho cả thiết bị di động (Mobile-first) và Desktop.

### Epic 2: Đặt vé & Xử lý thời gian thực (Core Booking)
- **Chọn suất chiếu:** Liệt kê các khung giờ và cụm rạp.
- **Sơ đồ ghế ngồi:** Hiển thị trực quan các loại ghế (Thường, VIP, Đôi).
- **Khóa ghế thời gian thực (Realtime Seat Locking):** Tránh trùng lặp khi nhiều người cùng chọn một ghế, tự động mở khóa sau khi hết thời gian giữ ghế (sử dụng Socket.io).
- **Thanh toán & Đặt vé (Checkout Flow):** Hiển thị tổng tiền, phương thức thanh toán, thông tin người dùng.
- **Vé điện tử (QR Ticket):** Tạo mã QR sau khi đặt vé thành công để quét khi vào rạp.

### Epic 3: Quản lý người dùng (Authentication & Profile)
- **Đăng ký/Đăng nhập:** Hỗ trợ xác thực bằng Email/Mật khẩu (JWT).
- **Quản lý hồ sơ (User Profile):** Cập nhật thông tin cá nhân, lịch sử giao dịch, danh sách vé đã đặt.
- **Cơ chế phân quyền:** Tách biệt quyền User (Người dùng) và Admin (Quản trị viên).

### Epic 4: Các tính năng mở rộng (Future Features)
- **Đánh giá & Bình luận phim (Reviews):** Người dùng có thể chấm điểm và viết review cho phim đã xem.
- **Cổng thanh toán thực (Payment Gateway):** Tích hợp VNPay, MoMo, ZaloPay, Stripe...
- **Hệ thống thông báo (Notifications):** Gửi email hoặc thông báo đẩy (push notifications) khi đặt vé thành công hoặc có phim mới.
- **Trang quản trị (Admin Dashboard):** Quản lý phim, rạp, suất chiếu, vé, và người dùng.
- **Thống kê & Phân tích (Analytics):** Báo cáo doanh thu, tỷ lệ lấp đầy phòng chiếu.

---

## 2. Product Backlog

Danh sách các công việc (User Stories) được sắp xếp theo mức độ ưu tiên từ cao xuống thấp.

### Sprint 1: Nền tảng (Foundation) & Authentication
- [ ] **STORY-101:** Là người dùng, tôi muốn xem Trang chủ với giao diện dark theme ấn tượng để có trải nghiệm điện ảnh chân thực.
- [ ] **STORY-102:** Là người dùng, tôi muốn xem danh sách Phim Đang Chiếu và Sắp Chiếu.
- [ ] **STORY-103:** Là hệ thống, cần thiết lập CSDL MongoDB với các schema cơ bản (Users, Movies, Showtimes).
- [ ] **STORY-104:** Là người dùng, tôi muốn đăng ký và đăng nhập vào hệ thống một cách an toàn.

### Sprint 2: Core Booking UI & Movie Details
- [ ] **STORY-201:** Là người dùng, tôi muốn xem Chi tiết phim (trailer, dàn cast, đánh giá) một cách trực quan.
- [ ] **STORY-202:** Là người dùng, tôi muốn xem lịch chiếu theo ngày và rạp để chọn suất phù hợp.
- [ ] **STORY-203:** Là người dùng, tôi muốn thấy sơ đồ ghế ngồi trực quan (chưa có realtime) để tiến hành chọn ghế.
- [ ] **STORY-204:** Là hệ thống, xây dựng các RESTful API phục vụ truy xuất thông tin phim và suất chiếu.

### Sprint 3: Realtime Seat Synchronization (Critical)
- [ ] **STORY-301:** Là hệ thống, tích hợp Socket.io vào sơ đồ ghế để báo trạng thái khóa ghế ngay lập tức.
- [ ] **STORY-302:** Là người dùng, tôi muốn thấy các ghế đang được người khác chọn chuyển màu để không bị chọn trùng.
- [ ] **STORY-303:** Là hệ thống, tự động giải phóng (unlock) ghế nếu người dùng ngắt kết nối (disconnect) hoặc quá thời gian thanh toán.
- [ ] **STORY-304:** Là hệ thống, lưu trữ chính thức vé vào CSDL sau khi luồng đặt vé hoàn tất.

### Sprint 4: Checkout, Tickets & Profile
- [ ] **STORY-401:** Là người dùng, tôi muốn xem trang Xác nhận đặt vé (Checkout) với đầy đủ thông tin số ghế, rạp, tổng tiền.
- [ ] **STORY-402:** Là người dùng, tôi muốn nhận được Vé điện tử có mã QR sau khi đặt vé thành công.
- [ ] **STORY-403:** Là người dùng, tôi muốn truy cập Hồ sơ cá nhân (Profile) để xem lại vé đã đặt.

### Sprint 5: Mở rộng (Admin & Thanh toán) - (Future)
- [ ] **STORY-501:** Là Admin, tôi muốn đăng nhập vào trang Dashboard (CMS) riêng.
- [ ] **STORY-502:** Là Admin, tôi muốn thêm/sửa/xóa thông tin Phim và Suất chiếu.
- [ ] **STORY-503:** Là người dùng, tôi muốn thanh toán bằng ví điện tử hoặc thẻ ngân hàng (MoMo/VNPay).
- [ ] **STORY-504:** Là người dùng, tôi muốn gửi đánh giá sao và bình luận cho bộ phim tôi vừa xem.
