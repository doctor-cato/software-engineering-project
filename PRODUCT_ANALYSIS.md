# Phân tích Sản phẩm (Product Analysis)

**Dự án:** 3HD2Kcinema - Ứng dụng đặt vé xem phim

## 1. Phân tích người dùng (User Analysis)
- **Đối tượng mục tiêu:** Sinh viên đại học, những người đam mê điện ảnh, thường xuyên đi xem phim cùng bạn bè hoặc gia đình.
- **Thói quen:** Thích xem trước review phim, đặt vé trực tuyến qua điện thoại di động, mua combo đồ ăn uống kèm vé để tiết kiệm thời gian.
- **Nhu cầu cốt lõi:** Một hệ thống đặt vé mượt mà, thao tác trực quan, thanh toán nhanh, và đặc biệt là có khả năng hỗ trợ đặt chỗ cho nhiều người cùng lúc mà không bị mất chỗ.

## 2. Xác định vấn đề (Problem Identification)
- **Vấn đề 1 (Đặt vé nhóm):** Khi một nhóm bạn đi xem phim, việc giữ nhiều ghế liền kề nhau và chia sẻ thanh toán (split bill) thường rất khó khăn trên các app hiện tại.
- **Vấn đề 2 (Đồng bộ ghế ngồi):** Hệ thống thường gặp lỗi "ghế ma" (ghost seats) hoặc bị double booking khi nhiều người cùng chọn một ghế tại cùng một thời điểm.
- **Vấn đề 3 (Thiếu tương tác):** Thiếu đi phần review thực tế từ người dùng khác ngay trên ứng dụng, khiến người xem khó ra quyết định chọn phim.

## 3. Chọn MVP (Minimum Viable Product)
Để giải quyết các vấn đề trên, phiên bản MVP của 3HD2Kcinema sẽ tập trung vào các tính năng cơ bản và giải quyết pain point chính:
- **Quản lý tài khoản (US01):** Đăng nhập/Đăng ký cơ bản.
- **Khám phá phim (US02):** Xem danh sách phim đang chiếu, sắp chiếu và xem review phim.
- **Đặt vé & Khóa ghế thời gian thực (US03):** Chức năng cốt lõi giúp chọn suất chiếu và khóa ghế ngay lập tức (Realtime seat locking) bằng Socket.io. Đặc biệt là tính năng "Split & Lock" cho nhóm.
- **Thanh toán & Hóa đơn (US05):** Thanh toán cơ bản và xuất vé QR.
- **Admin cơ bản (US07):** Quản lý suất chiếu, phim, và rạp.
