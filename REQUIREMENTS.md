# Requirements Document - 3HD2Kcinema

Dự án **3HD2Kcinema** là ứng dụng đặt vé xem phim trực tuyến thế hệ mới, hướng tới trải nghiệm tối giản, giao diện cinematic hiện đại và đồng bộ hóa thời gian thực.

Tài liệu này chi tiết hóa các yêu cầu nghiệp vụ dưới dạng các **Epic**, **User Stories** và tiêu chí nghiệm thu **Acceptance Criteria** theo định dạng BDD (Given-When-Then) nhằm làm rõ phạm vi phát triển cho phiên bản MVP.

---

## 1. Danh sách User Stories (US) theo Epics

### Epic 1: Quản lý Tài khoản & Cá nhân hóa
*   **US05: Đăng ký & Đăng nhập thành viên**
    *   *Mô tả:* Là khách vãng lai, tôi muốn đăng ký tài khoản và đăng nhập vào ứng dụng bằng email/mật khẩu, để lưu trữ lịch sử giao dịch và tích lũy điểm thưởng thành viên một cách an toàn.
*   **US08: Quản lý Hồ sơ, Lịch sử giao dịch & Tích điểm**
    *   *Mô tả:* Là khách hàng thành viên, tôi muốn xem thông tin hồ sơ cá nhân, lịch sử các giao dịch đặt vé trước đây và số điểm thưởng tích lũy (Loyalty Points), để tôi có thể quản lý chi tiêu và lên kế hoạch đổi thưởng.

### Epic 2: Tìm kiếm, Tra cứu & Chọn ghế (Aggregator & Real-time Seat Mapping)
*   **US01: Tra cứu thông tin phim & Lịch chiếu**
    *   *Mô tả:* Là một bạn trẻ bận rộn thường đi xem phim cuối tuần, tôi muốn tra cứu lịch chiếu, giá vé và thông tin phim trực quan, để tôi nhanh chóng chọn được suất chiếu phù hợp với thời gian và ngân sách của mình.
*   **US02: Sơ đồ phòng chiếu & Khóa ghế thời gian thực**
    *   *Mô tả:* Là một người kỹ tính khi đi xem phim rạp, tôi muốn thấy sơ đồ phòng chiếu trực quan theo thời gian thực và tự chọn vị trí ghế (Ghế thường, VIP hay Sweetbox), để tôi chắc chắn đặt được chỗ ngồi có góc nhìn đẹp nhất mà không lo bị trùng ghế với người khác.
*   **US09: Tìm kiếm & Lọc phim nâng cao**
    *   *Mô tả:* Là người dùng hệ thống, tôi muốn sử dụng công cụ tìm kiếm và bộ lọc đa chiều (theo tên phim, diễn viên, thể loại, khoảng thời gian), để tôi dễ dàng tìm thấy bộ phim yêu thích trong danh sách rạp đa dạng.
*   **US10: Bản đồ định vị cụm rạp (Cinema Map)**
    *   *Mô tả:* Là người xem phim tại các thành phố lớn, tôi muốn xem bản đồ định vị cụm rạp trực quan trên ứng dụng, để tôi biết khoảng cách thực tế và tìm đường đi đến rạp gần nhất thuận tiện.

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
*   **US11: [AI Feature] Gợi ý phim thông minh (AI Recommendation & Cine-Match)**
    *   *Mô tả:* Là một người dùng, tôi muốn trợ lý AI phân tích lịch sử giao dịch và đánh giá của tôi để tự động đề xuất những bộ phim phù hợp nhất, đồng thời gợi ý bạn ghép đôi có chung sở thích điện ảnh (Cine-Match).
*   **US12: [AI Feature] Tóm tắt đánh giá phim (AI Sentiment Summarizer)**
    *   *Mô tả:* Là một khán giả cần quyết định nhanh, tôi muốn AI tóm tắt tự động hàng ngàn bình luận của những người xem trước thành một đoạn văn đánh giá trung lập kèm theo chỉ số cảm xúc chung, để tôi nắm bắt chất lượng phim mà không phải đọc thủ công từng dòng bình luận.

---

## 2. Tiêu chí nghiệm thu chi tiết (Acceptance Criteria - BDD Format)

*(Bao gồm các US cốt lõi đại diện)*

### US01: Tra cứu thông tin phim & Lịch chiếu
*   **Kịch bản 1: Lọc phim theo thể loại**
    *   **Given (Cho):** Người dùng đang ở trang chủ Explore.
    *   **When (Khi):** Người dùng chọn một thể loại phim cụ thể (Ví dụ: "Hành động").
    *   **Then (Thì):** Hệ thống chỉ hiển thị danh sách các phim thuộc thể loại Hành động đang hoặc sắp chiếu.

### US02: Sơ đồ phòng chiếu & Khóa ghế thời gian thực
*   **Kịch bản 1: Đồng bộ ghế bị khóa bởi người khác (Real-time)**
    *   **Given:** Người dùng đang mở trang đặt vé cho suất chiếu `st_200`.
    *   **When:** Một người dùng khác ở tab khác click khóa ghế `A5`.
    *   **Then:** Trên màn hình của người dùng hiện tại, ghế `A5` lập tức chuyển sang màu xám `"Đã khóa (Locked)"` và không cho phép click chọn.
*   **Kịch bản 2: Tự động mở khóa khi hết hạn**
    *   **Given:** Người dùng đã khóa ghế `A5` nhưng chưa thanh toán.
    *   **When:** Hết thời gian giữ ghế 5 phút.
    *   **Then:** Trạng thái ghế `A5` lập tức được giải phóng về `"Trống (Available)"` và đồng bộ tới toàn bộ người dùng khác trong thời gian thực.

### US11: [AI Feature] Gợi ý phim thông minh (AI Recommendation)
*   **Kịch bản 1: Đề xuất phim chuẩn xác dựa trên lịch sử**
    *   **Given:** Người dùng đã từng đặt vé xem 3 phim thuộc thể loại "Hành động", "Khoa học viễn tưởng".
    *   **When:** Người dùng truy cập vào mục "Phim dành cho bạn".
    *   **Then:** AI gửi danh sách 5 bộ phim sắp chiếu có tag tương tự, kèm theo giải thích "Vì bạn đã xem Dune 2...".

### US12: [AI Feature] Tóm tắt đánh giá phim (AI Sentiment Summarizer)
*   **Kịch bản 1: Tóm tắt hàng trăm nhận xét về một bộ phim**
    *   **Given:** Bộ phim "Deadpool 3" có hơn 500 nhận xét từ người xem (cả khen và chê).
    *   **When:** Người dùng mở tab "Đánh giá & Bình luận" của phim.
    *   **Then:** Giao diện hiển thị một thẻ "AI Tổng hợp" bao gồm: 1 câu tóm lược nội dung khen nhiều nhất, 1 câu tóm lược điểm chê nhiều nhất, và biểu đồ cảm xúc (VD: 85% Tích cực).

---

## 3. Phạm vi sản phẩm MVP (Minimum Viable Product)

Để tối ưu hóa thời gian và năng suất làm việc của AI Agent, các tính năng được phân loại rõ ràng trong phạm vi MVP:

| Tính năng / Hạng mục | Trong phạm vi MVP | Ghi chú |
| :--- | :---: | :--- |
| **Đăng nhập / Đăng ký thành viên (JWT)** | **Có** | US05 |
| **Tra cứu phim, lịch chiếu & rạp** | **Có** | US01 |
| **Tìm kiếm & Lọc phim nâng cao** | **Có** | US09 |
| **Bản đồ cụm rạp (Cinema Map)** | **Có** | US10 |
| **Hồ sơ cá nhân & Lịch sử giao dịch** | **Có** | US08 |
| **Chọn ghế & Khóa ghế thời gian thực (Socket.io)** | **Có** | US02 - Cốt lõi bắt buộc |
| **Đặt bắp nước (Concessions)** | **Có** | US03 |
| **Cổng thanh toán trực tuyến** | **Có** | US04 |
| **Hóa đơn & Vé QR Code ngoại tuyến** | **Có** | US04 |
| Đặt vé nhóm & Chia tiền tự động (Split bill) | Không | Dành cho giai đoạn phát triển nâng cao (Post-MVP) |
| [AI Feature] Gợi ý phim & Cine-Match | Không | Dành cho giai đoạn phát triển nâng cao (Post-MVP) |
| [AI Feature] Tóm tắt đánh giá phim bằng AI | Không | Dành cho giai đoạn phát triển nâng cao (Post-MVP) |
