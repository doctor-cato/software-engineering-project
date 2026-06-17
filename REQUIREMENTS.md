# Requirements Document - 3HD2Kcinema

## 1. Personas
* **Persona 1 - Khách hàng cá nhân / Thích giao lưu:** Bạn Khánh, 19 tuổi, sinh viên. Ngân sách vừa phải, hay đi xem phim một mình nhưng lại có nhu cầu giao lưu, thích săn điểm thưởng giải trí trong lúc chờ vào phòng chiếu. Cần ứng dụng có giao diện đẹp, trực quan, tích hợp các tính năng cộng đồng và bản đồ gợi ý rạp chiếu phim ở gần.
* **Persona 2 - Người dùng đi theo nhóm:** Bạn Khương, 21 tuổi, sinh viên. Thường xuyên đứng ra lên lịch và đặt chỗ xem phim cho cả hội bạn thân. Khó khăn trong việc phải thu tiền thủ công của từng người, lo sợ bị người khác đặt mất ghế đẹp trong lúc chờ cả nhóm gom tiền, hoặc gặp rắc rối khi có thành viên hủy vé đột xuất. Cần tính năng giữ ghế và chia hóa đơn tự động.
* **Persona 3 - Thành viên đi theo nhóm:** Bạn Hùng, 20 tuổi, sinh viên. Thích đi xem phim chung với nhóm của Khương nhưng lịch trình học tập và làm thêm hay bị thay đổi đột xuất. Cần sự linh hoạt để có thể tự thanh toán phần của mình hoặc tự hủy vé cá nhân khi bận việc mà không làm ảnh hưởng đến suất chiếu và vị trí ghế ngồi của cả nhóm.
* **Persona Admin (Quản lý rạp):** Anh Minh, 32 tuổi, Quản lý vận hành. Đau đầu vì các ca giam ghế ảo, khó thống kê doanh thu từ các nguồn đặt vé combo nhóm để làm báo cáo cho tổng công ty.
* **Persona Staff (Nhân viên quầy):** Bạn Linh, 20 tuổi, sinh viên làm thêm tại quầy vé. Giờ cao điểm khách xếp hàng quá đông, mất thời gian kiểm tra từng mã giao dịch chia tiền của khách trên hệ thống cũ.

## 2. Scenario
* **Hoàn cảnh:** 7:00 tối thứ Sáu, nhóm bạn của Khương (Persona 2) và Hùng (Persona 3) quyết định đi xem một bộ phim bom tấn mới ra mắt. Do là cuối tuần, lượng người đặt vé rất đông và các vị trí ghế đẹp đang hết rất nhanh.
* **Câu chuyện:** Để chuẩn bị cho buổi xem phim cuối tuần, Khương dùng tính năng tìm kiếm nâng cao chọn suất chiếu rồi kích hoạt chế độ "Đặt và giữ ghế cho nhóm" để khóa trước 5 vị trí đẹp liền nhau. Ngay lập tức, hệ thống tự động phân chia hóa đơn về hồ sơ (profile) của từng người để Hùng và các thành viên khác chủ động vào tự bấm thanh toán phần mình. Trước giờ chiếu 45 phút, do bận việc đột xuất, Hùng vào profile cá nhân nhấn "Hủy vé của tôi"; nhờ mốc thời gian hợp lệ, hệ thống tự động hoàn tiền cho Hùng và giải phóng duy nhất vị trí ghế đó mà không làm ảnh hưởng đến vé của nhóm Khương. Sau suất chiếu, nhóm Khương chỉ cần quét mã QR vé để tham gia vào Box chat thảo luận ẩn danh để cùng đánh giá độ hài lòng về phim với những khán giả xem cùng suất chiếu.

## 3. User Stories
* **US1 (Đăng nhập & Cốt lõi):** Là một khách hàng, tôi muốn đăng nhập hệ thống và thực hiện tìm kiếm, lọc nâng cao để nhanh chóng tìm thấy bộ phim và suất chiếu phù hợp với lịch trình của mình.
* **US2 (Chọn dịch vụ):** Là một khách hàng, tôi muốn chọn vị trí ghế ngồi trực quan và đặt trước bỏng nước để không phải mất thời gian xếp hàng chờ đợi khi đến rạp.
* **US3 (Giữ ghế nhóm):** Là một trưởng nhóm, tôi muốn sử dụng tính năng đặt và giữ ghế cho nhóm để đảm bảo cả hội được ngồi cạnh nhau mà không sợ bị người khác mua mất chỗ trong lúc chờ các bạn thanh toán.
* **US4 (Tự động chia tiền):** Là một thành viên đi nhóm, tôi muốn thấy khoản tiền cần trả hiển thị riêng trong phần profile và có nút thanh toán độc lập để tôi chủ động sòng phẳng tiền bạc với trưởng nhóm.
* **US5 (Hủy vé cá nhân):** Là một người dùng đi nhóm, tôi muốn có nút tự hủy vé của riêng mình trong profile trước giờ chiếu ít nhất 30 phút để nhận lại tiền tự động mà không làm ảnh hưởng đến vé của các thành viên còn lại.
* **US6 (Nhận vé QR):** Là một người mua vé thành công, tôi muốn hệ thống hiển thị mã QR đặt vé và gửi bản sao về email để tôi lưu trữ, soát vé an toàn tại rạp.
* **US7 (Đánh giá sau phim):** Là một người vừa xem xong phim tôi muốn đánh giá phim ngay lập tức với những người xem cùng suất chiếu(đánh giá ?/5 sao).
* **US8 (Tiện ích giải trí):** Là một khách hàng cá nhân, tôi muốn tham gia chơi minigame CinePredict và tích lũy điểm thưởng.
