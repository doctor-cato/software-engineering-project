# UX/UI Prototype Overview - 3HD2Kcinema

Tài liệu này mô tả chi tiết kiến trúc, các thành phần giao diện, cơ chế hoạt động và cách vận hành của bản mẫu thử nghiệm (UI Prototype) được xây dựng cho dự án **3HD2Kcinema**.

Bản prototype này được thiết kế theo dạng **thuần Frontend (Server-free client-side)** sử dụng công nghệ cốt lõi Vanilla JS để mô phỏng chính xác các trải nghiệm người dùng cuối mà không phụ thuộc vào hệ thống Backend thực tế.

---

## 1. Công nghệ Sử dụng

*   **HTML5 & CSS3**: Cấu trúc và định kiểu nền tảng.
*   **Tailwind CSS (CDN)**: Cung cấp các class tiện ích để xây dựng giao diện hiện đại, tối giản, chuẩn điện ảnh.
*   **Vanilla JavaScript (ES6 Modules)**: Tổ chức logic mã nguồn theo hướng mô-đun hóa, dễ bảo trì và mở rộng.
*   **LocalStorage & SessionStorage**: Giả lập cơ sở dữ liệu lưu trữ tại Client để duy trì trạng thái của người dùng, phim, suất chiếu và lịch sử giao dịch.
*   **BroadcastChannel API**: Giả lập cơ chế giao tiếp thời gian thực (real-time) giữa các tab trình duyệt khác nhau phục vụ tính năng khóa ghế.
*   **qrcode.js**: Tạo mã QR Code động hiển thị thông tin vé tích hợp tại trang hóa đơn.
*   **Leaflet.js**: Bản đồ tương tác hiển thị định vị và đường đi tới các cụm rạp.

---

## 2. Kiến trúc Module Dựa trên Tính năng (Domain-Based Architecture)

Mã nguồn của prototype được tổ chức phân rã theo từng lĩnh vực nghiệp vụ cụ thể thay vì gom nhóm theo loại tệp. Cách tiếp cận này giúp việc nâng cấp lên các framework như React/Next.js trong tương lai được diễn ra thuận lợi:

```text
src/
├── index.html               # Trang điều hướng chính (Redirect)
├── auth/                    # Domain: Xác thực tài khoản
│   ├── user-login/          # Giao diện đăng nhập
│   └── user-register/       # Giao diện đăng ký
├── booking/                 # Domain: Quy trình đặt vé
│   ├── seat-booking/        # Chọn ghế ngồi thời gian thực
│   ├── booking-food/        # Mua kèm bỏng ngô & nước uống
│   └── checkout/            # Thanh toán & Hóa đơn điện tử QR
├── explore/                 # Domain: Khám phá
│   ├── home-page/           # Trang chủ giới thiệu phim & lịch chiếu
│   ├── movie-search/        # Tìm kiếm & Lọc phim nâng cao
│   └── cinema-map/          # Bản đồ định vị cụm rạp
├── user/                    # Domain: Hồ sơ & Cá nhân hóa
│   ├── user-profile/        # Thông tin cá nhân
│   └── loyalty-points/      # Hệ thống tích lũy điểm thưởng
└── shared/                  # Thư mục dùng chung
    ├── components/          # Thanh điều hướng (Navbar), Footer dùng chung
    ├── css/                 # Cấu hình phong cách hiển thị hệ thống
    └── utils/               # Tiện ích chung (storage.js xử lý Mock DB)
```

---

## 3. Cơ chế Vận hành Cốt lõi

### A. Giả lập Cơ sở Dữ liệu (Mock DB)
Toàn bộ thao tác đọc/ghi dữ liệu đều thông qua dịch vụ dùng chung `shared/utils/storage.js` thay vì gọi trực tiếp `localStorage.setItem` tại các trang đơn lẻ.
*   **`users_db`**: Mảng chứa thông tin tài khoản người dùng đã đăng ký.
*   **`movies_db`**: Danh sách thông tin chi tiết phim (ảnh poster, thể loại, thời lượng, lịch chiếu).
*   **`seat_status_db`**: Từ điển (Map) lưu trữ trạng thái chi tiết của từng ghế ngồi ứng với mỗi suất chiếu (`available`, `locked`, `booked`).
*   **`active_session`**: (SessionStorage) Lưu vết phiên đăng nhập của người dùng hiện tại để đồng bộ giao diện Navbar.
*   **`pending_checkout`**: (SessionStorage) Lưu giữ thông tin giỏ hàng tạm thời khi người dùng chuyển tiếp từ trang đặt vé sang trang thanh toán.

### B. Khóa Ghế Thời gian thực (Real-time Seat Locking)
Để giải quyết bài toán trùng ghế khi có hàng trăm người dùng cùng thao tác đồng thời:
1.  Khi người dùng click vào một ghế trống, trạng thái ghế đổi sang `locked` trong `seat_status_db` và bắt đầu đếm ngược 5 phút.
2.  Một thông điệp khóa được phát đi thông qua `BroadcastChannel('seat_sync')` với nội dung dạng: `{ type: 'LOCK_SEAT', seatId: 'A5', showtimeId: 'st_200' }`.
3.  Tất cả các tab trình duyệt khác đang mở trang đặt vé cho suất chiếu đó sẽ nhận sự kiện này và đổi màu ghế tương ứng thành màu xám (không cho phép chọn).
4.  Nếu hết 5 phút mà người dùng chưa thanh toán xong, hoặc nếu người dùng tắt tab (bắt sự kiện `beforeunload`), ghế sẽ tự động được mở khóa và phát đi thông điệp `{ type: 'UNLOCK_SEAT' }` để đồng bộ lại.
5.  **Mô phỏng Bot**: Trong trang đặt ghế có tích hợp mã giả lập Bot (`setInterval`) tự động khóa/mở khóa ngẫu nhiên một số ghế sau vài giây nhằm giúp người kiểm thử thấy rõ sự thay đổi giao diện theo thời gian thực mà không cần mở nhiều tab.

### C. Quy trình Thanh toán & Xuất vé QR Code
1.  Sau khi chọn ghế và combo bắp nước, thông tin đơn hàng được đẩy vào `pending_checkout`.
2.  Người dùng chuyển tới trang thanh toán, lựa chọn cổng thanh toán (MoMo/VNPAY giả lập).
3.  Ứng dụng chuyển hướng sang trang mô phỏng thanh toán, sau khi click xác nhận thành công:
    *   Trạng thái ghế của suất chiếu được cập nhật nguyên tử (atomic update) thành `booked`.
    *   Đơn hàng được lưu vào lịch sử đặt vé của người dùng.
    *   Người dùng được chuyển hướng tới trang hóa đơn `booking_invoice.html`.
4.  Tại trang hóa đơn, dữ liệu giao dịch được mã hóa thành một chuỗi băm độc nhất. Thư viện `qrcode.js` sẽ vẽ mã QR Code động trực quan trên màn hình. Người dùng có thể quét thử mã QR này bằng điện thoại để xem thông tin vé đã đặt.

---

## 4. Hướng dẫn Khởi chạy Cục bộ

Do các tập tin JavaScript được thiết kế dưới dạng ES6 Modules (`type="module"`), trình duyệt sẽ chặn yêu cầu nếu mở file trực tiếp dạng `file:///` do chính sách CORS. Bạn bắt buộc phải chạy qua một HTTP Server tĩnh:

### Cách 1: Sử dụng Python (Có sẵn trên máy)
1. Mở Terminal tại thư mục `src/` của dự án prototype.
2. Chạy lệnh:
   ```bash
   python -m http.server 8000
   ```
3. Truy cập địa chỉ `http://localhost:8000/index.html` trên trình duyệt.

### Cách 2: Sử dụng VSCode Live Server Extension
1. Mở thư mục dự án prototype bằng VSCode.
2. Cài đặt tiện ích mở rộng (Extension) **Live Server**.
3. Chuột phải vào tệp `src/index.html` và chọn **Open with Live Server**.
