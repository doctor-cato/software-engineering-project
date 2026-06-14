# Requirements Document - 3HD2Kcinema

Dự án **3HD2Kcinema** là ứng dụng đặt vé xem phim trực tuyến thế hệ mới, hướng tới trải nghiệm tối giản, giao diện cinematic hiện đại và đồng bộ hóa thời gian thực.

Tài liệu này chi tiết hóa các yêu cầu nghiệp vụ dưới dạng các **Epic**, **User Stories** và tiêu chí nghiệm thu **Acceptance Criteria** theo định dạng BDD (Given-When-Then) nhằm làm rõ phạm vi phát triển cho phiên bản MVP.

---

## 1. Danh sách User Stories (US) theo Epics

### Epic 1: Quản lý Tài khoản & Cá nhân hóa
*   **US05: Đăng ký & Đăng nhập thành viên**
    *   *Mô tả:* Là khách vãng lai, tôi muốn đăng ký tài khoản và đăng nhập vào ứng dụng bằng email/mật khẩu, để lưu trữ lịch sử giao dịch và tích lũy điểm thưởng thành viên một cách an toàn.

### Epic 2: Tìm kiếm, Tra cứu & Chọn ghế (Aggregator & Real-time Seat Mapping)
*   **US01: Tra cứu thông tin phim & Lịch chiếu**
    *   *Mô tả:* Là một bạn trẻ bận rộn thường đi xem phim cuối tuần, tôi muốn tra cứu lịch chiếu, giá vé và thông tin phim trực quan, để tôi nhanh chóng chọn được suất chiếu phù hợp với thời gian và ngân sách của mình.
*   **US02: Sơ đồ phòng chiếu & Khóa ghế thời gian thực**
    *   *Mô tả:* Là một người kỹ tính khi đi xem phim rạp, tôi muốn thấy sơ đồ phòng chiếu trực quan theo thời gian thực và tự chọn vị trí ghế (Ghế thường, VIP hay Sweetbox), để tôi chắc chắn đặt được chỗ ngồi có góc nhìn đẹp nhất mà không lo bị trùng ghế với người khác.

### Epic 3: Dịch vụ mở rộng & Thanh toán (Snack Booking & Payment Gateway)
*   **US03: Đặt trước Combo bắp nước (Concessions up-sell)**
    *   *Mô tả:* Là một khách hàng yêu thích sự tiện lợi, tôi muốn chọn mua các gói combo bắp nước ưu đãi trực quan ngay trong quy trình checkout đặt vé, để tôi thanh toán trước và rút ngắn tối đa thời gian xếp hàng chờ đợi nhận đồ ăn tại quầy rạp.
*   **US04: Thanh toán trực tuyến & Hóa đơn QR Code ngoại tuyến**
    *   *Mô tả:* Là thành viên thích giao dịch nhanh gọn, tôi muốn thanh toán trực tuyến an toàn qua ví điện tử (MoMo/VNPAY) và nhận ngay vé điện tử QR Code tích hợp hiển thị ngoại tuyến, để hoàn tất quy trình giao dịch nhanh chóng và soát vé tiện lợi tại rạp mà không cần in vé giấy.

### Epic 4: Tương tác xã hội & Quản trị rạp (Social Features & Admin Management)
*   **US06: Đặt vé nhóm & Tự động chia hóa đơn (Split & Lock)**
    *   *Mô tả:* Là một sinh viên thường đi xem phim chung với hội bạn thân, tôi muốn sử dụng tính năng "Booking Nhóm" (Split & Lock) để cùng chọn ghế và tự động chia đều hóa đơn khi thanh toán, để chúng tôi ngồi cạnh nhau mà không gặp cảnh ngại ngùng khi phải gom tiền thủ công.
*   **US07: Đánh giá phim & Bảng điều khiển Admin**
    *   *Mô tả:* Là thành viên tích cực, tôi muốn gửi đánh giá sao và bình luận nhận xét về bộ phim sau khi xem xong; và là Admin, tôi muốn có giao diện quản lý phim, rạp và suất chiếu trực quan để điều phối hoạt động rạp chiếu hiệu quả.

---

## 2. Tiêu chí nghiệm thu chi tiết (Acceptance Criteria - BDD Format)

### US01: Tra cứu thông tin phim & Lịch chiếu
*   **Kịch bản 1: Lọc phim theo thể loại**
    *   **Given (Cho):** Người dùng đang ở trang chủ Explore.
    *   **When (Khi):** Người dùng chọn một thể loại phim cụ thể (Ví dụ: "Hành động").
    *   **Then (Thì):** Hệ thống chỉ hiển thị danh sách các phim thuộc thể loại Hành động đang hoặc sắp chiếu.
*   **Kịch bản 2: Xem chi tiết phim**
    *   **Given:** Người dùng quan tâm đến một bộ phim bất kỳ trên danh sách.
    *   **When:** Người dùng click vào poster của phim đó.
    *   **Then:** Hệ thống hiển thị trang thông tin chi tiết phim bao gồm: trailer, mô tả, diễn viên, thời lượng, điểm đánh giá và danh sách lịch chiếu chia theo từng cụm rạp.

### US02: Sơ đồ phòng chiếu & Khóa ghế thời gian thực
*   **Kịch bản 1: Ghế được chọn bởi chính người dùng**
    *   **Given:** Người dùng đang ở màn hình chọn ghế cho suất chiếu `st_200`.
    *   **When:** Người dùng click vào một ghế trống có trạng thái `available` (Ví dụ: Ghế A5).
    *   **Then:** Trạng thái ghế đổi sang màu cam thể hiện `"Đã chọn (Selected)"` và đồng hồ đếm ngược giữ ghế 5 phút bắt đầu hiển thị.
*   **Kịch bản 2: Đồng bộ ghế bị khóa bởi người khác (Real-time)**
    *   **Given:** Người dùng đang mở trang đặt vé cho suất chiếu `st_200`.
    *   **When:** Một người dùng khác ở tab khác click khóa ghế `A5`.
    *   **Then:** Trên màn hình của người dùng hiện tại, ghế `A5` lập tức chuyển sang màu xám `"Đã khóa (Locked)"` và không cho phép click chọn.
*   **Kịch bản 3: Tự động mở khóa khi hết hạn hoặc tắt trình duyệt**
    *   **Given:** Người dùng đã khóa ghế `A5` nhưng chưa thanh toán.
    *   **When:** Hết thời gian giữ ghế 5 phút HOẶC người dùng tắt trình duyệt/đóng tab.
    *   **Then:** Trạng thái ghế `A5` lập tức được giải phóng về `"Trống (Available)"` và đồng bộ tới toàn bộ người dùng khác trong thời gian thực.

### US03: Mua combo bắp nước
*   **Kịch bản 1: Thêm combo F&B tại màn hình chọn đồ ăn**
    *   **Given:** Người dùng đã khóa ghế thành công và chuyển sang bước mua bắp nước.
    *   **When:** Người dùng click chọn `"Combo Double (1 Bắp + 2 Nước)"`.
    *   **Then:** Hệ thống hiển thị chi tiết giá trị combo, cập nhật tổng số tiền tạm tính của giỏ hàng và hiển thị nút chuyển sang bước thanh toán.

### US04: Thanh toán trực tuyến & Vé QR
*   **Kịch bản 1: Giao dịch thanh toán thành công**
    *   **Given:** Người dùng đang ở màn hình Checkout với giỏ hàng chứa thông tin ghế và bắp nước tạm tính.
    *   **When:** Người dùng chọn thanh toán bằng ví MoMo và click xác nhận thanh toán thành công ở cổng giả lập.
    *   **Then:** Hệ thống cập nhật vĩnh viễn trạng thái các ghế đã chọn từ `locked` sang `booked` trong CSDL, lưu giao dịch vào lịch sử và chuyển hướng người dùng sang trang hóa đơn hiển thị mã QR động chứa thông tin vé.

### US06: Đặt vé nhóm (Split & Lock) - Tính năng Nâng cao
*   **Kịch bản 1: Khởi tạo luồng đặt vé nhóm**
    *   **Given:** Người dùng Đức đang ở sơ đồ chọn ghế.
    *   **When:** Đức chọn tính năng `"Đặt vé nhóm"` và chọn 4 ghế `A1, A2, A3, A4` liền kề.
    *   **Then:** Hệ thống khóa tạm thời 4 ghế này trong 15 phút, đồng thời tạo ra một liên kết thanh toán nhóm (Group Link) hiển thị trên màn hình.
*   **Kịch bản 2: Các thành viên nhóm tự thanh toán**
    *   **Given:** Các thành viên trong nhóm nhận được liên kết thanh toán từ Đức.
    *   **When:** Từng thành viên click vào liên kết, chọn vị trí ghế của mình trong cụm ghế đã khóa và hoàn tất thanh toán phần tiền tương ứng qua ví điện tử.
    *   **Then:** Trạng thái ghế của thành viên đó chuyển sang `booked`. Khi tất cả thành viên hoàn tất, hệ thống chính thức xác nhận giao dịch nhóm thành công và gửi vé QR đến cho từng người.

---

## 3. Phạm vi sản phẩm MVP (Minimum Viable Product)

Để tối ưu hóa thời gian và năng suất làm việc của AI Agent, các tính năng được phân loại rõ ràng trong phạm vi MVP:

| Tính năng / Hạng mục | Trong phạm vi MVP | Ghi chú |
| :--- | :---: | :--- |
| Đăng nhập / Đăng ký thành viên (JWT) | **Có** | Cần để lưu lịch sử và tích điểm |
| Tra cứu phim, lịch chiếu & rạp | **Có** | Giao diện tối giản, trực quan |
| Chọn ghế & Khóa ghế thời gian thực (Socket.io) | **Có** | Tính năng cốt lõi bắt buộc |
| Đặt bắp nước (Concessions) | **Có** | Tích hợp trong luồng đặt vé |
| Cổng thanh toán trực tuyến | **Có** | Mô phỏng hoặc tích hợp giả lập |
| Hóa đơn & Vé QR Code ngoại tuyến | **Có** | Dùng QR Code phía Client |
| Bản đồ cụm rạp | **Có** | Tích hợp thư viện Leaflet.js bản đồ |
| Đặt vé nhóm & Chia tiền tự động (Split bill) | Không | Dành cho giai đoạn phát triển nâng cao (Post-MVP) |
| Cine-Match (Ghép đôi xem phim) | Không | Dành cho giai đoạn phát triển nâng cao (Post-MVP) |
| Cinebet Minigame | Không | Dành cho giai đoạn phát triển nâng cao (Post-MVP) |
| Thảo luận & Đánh giá phim sau khi xem | Không | Dành cho giai đoạn phát triển nâng cao (Post-MVP) |
