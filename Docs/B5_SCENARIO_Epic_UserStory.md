**BƯỚC 5: XÁC ĐỊNH SCENARIO, EPIC VÀ USER STORY**

**1\. Kịch bản sử dụng (Scenario)**

Đây là các kịch bản thực tế mô tả chi tiết cách người dùng mục tiêu tương tác với hệ thống để giải quyết các khó khăn cụ thể của họ.

* **Kịch bản 1: Đi xem phim cuối tuần cùng hội bạn thân (Giải quyết bài toán chia tiền \- Split & Lock)**  
  * Minh là sinh viên, thường xuyên lên lịch đi xem phim với nhóm bạn 4 người. Minh mở ứng dụng 3HD2Kcinema, tra cứu lịch chiếu và so sánh giá vé giữa các rạp.  
  * Thông thường, một người sẽ phải đứng ra ứng tiền trước để đặt cả cụm ghế cạnh nhau, sau đó lại mất công tính toán và đòi tiền từng người rất ngại ngùng.  
  * Để giải quyết, khi chọn được rạp và suất chiếu, Minh dùng tính năng "Booking Nhóm" (Split & Lock) để chọn và tạm khóa 4 ghế liền nhau trong 15 phút. Hệ thống sinh ra một đường link, Minh gửi link này cho 3 người bạn kia để từng thành viên tự vào thanh toán phần vé của mình.  
  * Sau khi cả 4 thanh toán xong, hệ thống chốt ghế và xuất vé điện tử, giúp cả nhóm có chỗ ngồi đẹp mà không gặp cảnh ngại ngùng gom tiền thủ công sau buổi đi chơi.  
* **Kịch bản 2: Đi hẹn hò và tối ưu hóa thời gian tại rạp (Tích hợp Seat Mapping & F\&B)**  
  * Lan là nhân viên văn phòng bận rộn. Cuối tuần, cô muốn đi xem phim cùng người yêu. Lan mở app, xem sơ đồ phòng chiếu trực quan theo thời gian thực và chọn ngay ghế Sweetbox có góc nhìn đẹp nhất. Điều này giúp Lan tránh tình trạng ra đến rạp mới xếp hàng thì chỉ còn lại ghế góc khuất.  
  * Do cực kỳ ngại việc sau khi xếp hàng soát vé xong lại phải tiếp tục xếp hàng lần thứ hai tại quầy bắp nước vào giờ cao điểm, Lan đặt kèm "Combo Couple" (bắp và nước) trực tiếp trong luồng thanh toán.  
  * Cô thanh toán qua ví điện tử và nhận về một mã QR Code tổng hợp duy nhất cho cả vé và combo bắp nước. Đến rạp, Lan chỉ cần đưa mã QR ra quét một lần để vừa vào cửa vừa lấy đồ ăn nhanh chóng.

**2\. Nhóm tính năng lớn (Epic)**

Hệ thống 3HD2Kcinema được phân rã thành 4 Epic (chủ đề) cốt lõi bao quát toàn bộ các tính năng từ cơ bản đến nâng cao:

* **Epic 1: Quản lý Tài khoản & Cá nhân hóa**  
  * Bao gồm đăng ký, đăng nhập, quản lý lịch sử giao dịch, khôi phục mật khẩu và hệ thống tích điểm hạng thành viên.  
* **Epic 2: Tìm kiếm, Tra cứu tổng hợp & Sơ đồ ghế thực tế (Aggregator & Real-time Seat Mapping)**  
  * Bao gồm xem danh sách phim, tra cứu cụm rạp, chọn suất chiếu và thao tác trên sơ đồ ghế ngồi thời gian thực.  
  * Cho phép người dùng tra cứu tất cả thông tin trên một giao diện duy nhất thay vì phải tải và mở từng ứng dụng riêng lẻ của CGV, Lotte hay BHD.  
* **Epic 3: Dịch vụ mở rộng & Thanh toán (Tích hợp F\&B Upsell)**  
  * Bao gồm đặt kèm F\&B (bắp nước), cổng thanh toán trực tuyến đa nền tảng và hệ thống xuất vé điện tử E-Ticket dưới dạng QR Code.  
* **Epic 4: Tương tác xã hội & AI (Tính năng khác biệt)**  
  * Bao gồm chức năng Booking nhóm tự động chia tiền, đánh giá phim, ghép đôi xem phim (Cine-Match) và trợ lý ảo AI gợi ý phim.

**3\. Câu chuyện người dùng chi tiết (User Story)**

Dưới đây là các User Story quan trọng được triển khai từ các Epic, bám sát nhu cầu và mang lại giá trị cao nhất cho người dùng:

**Thuộc Epic 2 (Tìm kiếm & Chọn ghế):**

* **US01:** Là một bạn trẻ bận rộn thường đi xem phim cuối tuần, tôi muốn có thể tra cứu và so sánh lịch chiếu, giá vé của tất cả các cụm rạp (CGV, Lotte, BHD...) cùng lúc trên một ứng dụng duy nhất, để tôi nhanh chóng chọn được suất chiếu phù hợp nhất với thời gian và ngân sách của mình mà không cần phải mở từng app riêng lẻ.  
* **US02:** Là một người kỹ tính khi đi xem phim rạp, tôi muốn xem được sơ đồ phòng chiếu trực quan theo thời gian thực và tự chọn vị trí ghế (Ghế thường, VIP hay Sweetbox), để tôi chắc chắn đặt được chỗ ngồi có góc nhìn đẹp nhất mà không lo bị trùng ghế với người khác hoặc phải xếp hàng chờ đợi tại quầy.

**Thuộc Epic 3 (Thanh toán & Dịch vụ F\&B):**

* **US03:** Là một khách hàng yêu thích sự tiện lợi, tôi muốn chọn mua các gói combo bắp nước ưu đãi trực quan ngay trong quy trình check-out đặt vé, để tôi nhận được một mã QR tổng hợp duy nhất giúp lấy đồ ăn và soát vé nhanh chóng tại rạp.  
* **US04:** Là khách hàng thích ăn vặt, tôi muốn hệ thống tích hợp menu chọn các gói bắp, nước, combo ưu đãi để tôi có thể thanh toán trước, giúp giảm thời gian xếp hàng chờ đợi tại quầy rạp.  
* **US05:** Là người mua vé, tôi muốn có cổng thanh toán trực tuyến (Ví điện tử, thẻ ngân hàng) và trả về mã vé QR Code ngay sau khi mua thành công, để tôi lưu trữ ngay trên điện thoại và soát vé nhanh chóng.

**Thuộc Epic 4 (Tương tác xã hội):**

* **US06:** Là một sinh viên thường xuyên lên lịch đi xem phim chung với hội bạn thân, tôi muốn sử dụng tính năng "Booking Nhóm" để gửi lời mời chọn ghế chung và tự động chia đôi/chia đều hóa đơn (Split bill) ngay khi thanh toán, để chúng tôi có thể ngồi cạnh nhau trong rạp và không gặp cảnh ngại ngùng khi phải gom tiền hay tính toán thủ công sau buổi đi chơi.

 

