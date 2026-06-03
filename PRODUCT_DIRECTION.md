# Định hướng Sản phẩm (Product Direction)

**Dự án:** 3HD2Kcinema - Ứng dụng đặt vé xem phim.

## 1. Hướng đi đã chọn (Project Direction)
Dựa trên các tùy chọn của Tuần 1, hướng đi được chọn cho dự án này là: **Làm app mới (Build from scratch).**
Mục tiêu là xây dựng mới hoàn toàn một hệ thống đặt vé xem phim chuyên nghiệp. Định hướng phát triển luôn xoay quanh nhu cầu của các Persona chung: những người đam mê điện ảnh, thường xuyên đi xem phim theo nhóm, và mong muốn có trải nghiệm đặt vé nhanh chóng, tiện lợi qua thiết bị di động.

## 2. Các tính năng cốt lõi (Chuẩn hóa theo Docs/MD type)
- **US01:** Cinematic UI & Movie Browse (Khám phá phim & lịch chiếu trực quan).
- **US02:** Real-time Seat Locking (Khóa ghế thời gian thực - đề xuất dùng Socket.io).
- **US03:** Snack Booking (Đặt trước bắp nước).
- **US04:** Payment & QR Ticket (Thanh toán & Vé điện tử QR).
- **US05:** Authentication & JWT (Đăng ký / Đăng nhập thành viên).
- **US06:** Split & Lock (Booking nhóm & Chia tiền tự động).
- **US07:** Reviews & Admin Dashboard (Đánh giá phim & Bảng điều khiển quản trị - bỏ qua ở phiên bản hiện tại).

## 3. Mục tiêu và Tầm nhìn (Goals & Vision)
- **Kiến trúc:** Giữ vững triết lý phát triển sạch sẽ, dạng module, dễ đọc và dễ mở rộng. Tránh tình trạng "overengineering" (thiết kế quá mức cần thiết).
- **Trải nghiệm người dùng (UX):** Xây dựng UI/UX theo hướng "cinematic dark UI", thêm các hiệu ứng chuyển cảnh mượt mà để tăng tính tương tác.
- **Tính năng trọng tâm:** Đảm bảo hệ thống khóa ghế realtime hoạt động hoàn hảo không lỗi lầm (zero ghost seats, no double bookings).
- **Mở rộng (AI & Tương lai):** Chuẩn bị nền tảng để tích hợp các tính năng AI (Gợi ý phim, AI Chatbot) và Dashboard thống kê chuyên sâu ở các phase tiếp theo.
