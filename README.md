# 3HD2Kcinema - Online Movie Ticket Booking Application

[![GitHub Issues](https://img.shields.io/github/issues/doctor-cato/software-engineering-project)](https://github.com/doctor-cato/software-engineering-project/issues)
[![Platform](https://img.shields.io/badge/platform-Web%20%7C%20Mobile-blue.svg)]()

**3HD2Kcinema** là ứng dụng đặt vé xem phim trực tuyến thế hệ mới, hướng tới trải nghiệm siêu tiện lợi, tối giản hóa quy trình tương tác và tối ưu hóa thời gian cho người dùng yêu thích điện ảnh.

---

##  Tầm nhìn sản phẩm (Product Vision)

*   **Dành cho (FOR):** Học sinh, sinh viên và người đi làm trẻ (15-35 tuổi) có lối sống hiện đại, yêu thích trải nghiệm điện ảnh.
*   **Giải quyết vấn đề (WHO):** Những người mệt mỏi với các ứng dụng đặt vé rườm rà, tải chậm, mất thời gian xếp hàng mua vé/đồ ăn trực tiếp tại quầy vào giờ cao điểm, hoặc gặp sự cố trùng ghế khi đặt online.
*   **Giải pháp (THE 3HD2Kcinema IS A):** Ứng dụng đặt vé xem phim trực tuyến thế hệ mới với quy trình tối giản.
*   **Giá trị mang lại (THAT):** Tối ưu hóa thời gian thông qua việc tra cứu lịch chiếu trực quan, chọn vị trí chỗ ngồi chính xác và thanh toán không tiền mặt chỉ dưới 2 phút.
*   **Điểm khác biệt (UNLIKE):** Khác biệt hoàn toàn so với các trang web rạp đơn lẻ thường nghẽn mạng khi có bom tấn hoặc quy trình mua vé giấy/bắp nước vật lý phức tạp.
*   **Tính năng nổi bật (OUR PRODUCT):** Sở hữu thuật toán khóa ghế đồng bộ thời gian thực (Socket.io), tích hợp đặt trước bắp nước chung mã QR, hỗ trợ hiển thị vé ngoại tuyến (Offline QR Code) và đặt vé nhóm tự động chia tiền (Split bill).

---

##  Các tính năng cốt lõi (Key Features)

Dự án được phân rã thành các Epic và User Story (từ US01 đến US06) để phát triển:

###  1. Cinematic UI & Movie Browse (US01)
*   Giao diện rạp phim điện ảnh trực quan.
*   Tra cứu thông tin phim, lịch chiếu và giá vé trực quan, thuận tiện.

###  2. Real-time Seat Locking (US02)
*   Sơ đồ phòng chiếu tương tác thời gian thực sử dụng **Socket.io**.
*   Hiển thị ghế người khác đang chọn và tạm khóa ghế đang chọn trong 5 phút để tránh trùng ghế.

###  3. Snack Booking & Up-sell (US03)
*   Chọn mua các gói combo bắp nước ưu đãi trực quan ngay trong quy trình thanh toán vé.
*   Tiết kiệm thời gian xếp hàng tại quầy F&B.

###  4. Payment & QR Ticket (US04)
*   Tích hợp thanh toán trực tuyến an toàn qua ví điện tử (MoMo/VNPAY).
*   Xuất vé điện tử QR Code tích hợp (vé + bắp nước) hỗ trợ xem ngoại tuyến khi không có kết nối mạng.

###  5. Authentication & JWT (US05)
*   Đăng ký và Đăng nhập thành viên để lưu lịch sử giao dịch và tích điểm.

###  6. Booking Nhóm & Chia tiền tự động (US06)
*   Tính năng **Split & Lock** giúp giữ chỗ chung cho cả nhóm bạn và tự động chia đều hóa đơn thanh toán trực tuyến riêng lẻ.

---

##  Công nghệ sử dụng (Tech Stack)

*(Đang trong quá trình khảo sát và chưa chốt phương án công nghệ chính thức)*

Dưới đây là một số đề xuất công nghệ dự kiến cân nhắc sử dụng:
*   **Frontend:** HTML, CSS, JavaScript (cân nhắc React / Next.js / Vite)
*   **Backend:** Node.js, Express
*   **Real-time Communication:** Socket.io (phục vụ tính năng khóa ghế thời gian thực)
*   **Database:** MongoDB / Relational Database
*   **Authentication:** JWT (JSON Web Token)
*   **Payment Gateway:** Giả lập hoặc tích hợp MoMo / VNPAY APIs

---

##  Cấu trúc thư mục tài liệu

Thông tin phân tích và thiết kế chi tiết dự án có thể tham khảo tại thư mục `Docs/MD_Type/`:
*   [B3_Persona_UserJourney.md](Docs/MD_Type/B3_Persona_UserJourney.md): Chân dung khách hàng mục tiêu & Hành trình người dùng.
*   [B4_Product_Vision.md](Docs/MD_Type/B4_Product_Vision.md): Định vị tầm nhìn sản phẩm.
*   [B5_SCENARIO_Epic_UserStory.md](Docs/MD_Type/B5_SCENARIO_Epic_UserStory.md): Kịch bản sử dụng, Epic và chi tiết User Stories.
*   [B6_Product_BackLog.md](Docs/MD_Type/B6_Product_BackLog.md): Danh sách tính năng và Product Backlog ưu tiên.

---

##  Hướng dẫn đóng góp (Contributing Guide)

Xem chi tiết quy trình Git Workflow, cách đặt tên nhánh (branch), chuẩn commit message và tạo Pull Request (PR) tại tài liệu hướng dẫn:
*   [CONTRIBUTING.md](CONTRIBUTING.md)
