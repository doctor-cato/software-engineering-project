# Nhật ký Phát triển - Tuần 3 (Week 03)

**Giai đoạn:** Khảo sát Codebase/UI Prototype & Chuẩn hóa Tài liệu Yêu cầu (Requirements)

## 1. Các hoạt động đã thực hiện

*   **Khảo sát UI Prototype có sẵn:**
    *   Tiến hành phân tích chi tiết mã nguồn bản mẫu (UI Prototype) thuần Frontend được xây dựng tại thư mục `C:\Users\Admin\Documents\CODE_WORKSPACE\web-application-development`.
    *   Đánh giá kiến trúc phân nhóm theo tính năng (Domain-Based Architecture) của bản prototype bao gồm các thư mục `auth`, `booking`, `explore`, `user`, và `shared`.
    *   Thử nghiệm chạy cục bộ ứng dụng bằng máy chủ HTTP tĩnh (Live Server trong VSCode) và kiểm chứng tính năng khóa ghế thời gian thực giả lập bằng `BroadcastChannel API` cùng vòng lặp Bot tự động chọn ghế.
*   **Xây dựng tài liệu mô tả UX Prototype:**
    *   Viết tài liệu `UX_PROTOTYPE.md` mô tả toàn bộ cấu trúc thư mục, kiến trúc Client-side, cơ chế giả lập cơ sở dữ liệu trên bộ nhớ trình duyệt (`LocalStorage`, `SessionStorage`), thuật toán giữ ghế tạm thời trong 5 phút và cơ chế tạo QR Code động cho vé điện tử.
*   **Chuẩn hóa tài liệu yêu cầu (Requirements document):**
    *   Xây dựng file `REQUIREMENTS.md` chi tiết hóa 7 User Stories cốt lõi tương ứng với 4 Epic lớn của dự án `3HD2Kcinema`.
    *   Viết các kịch bản kiểm thử nghiệm thu chi tiết dưới định dạng BDD (Given-When-Then) cho các tính năng quan trọng như lọc phim, xem chi tiết phim, khóa ghế thời gian thực, đặt bắp nước và thanh toán tạo QR.
    *   Xác định rõ phạm vi các tính năng sẽ đưa vào phiên bản MVP và các tính năng nâng cao (như Booking nhóm tự chia tiền, Cine-Match, Minigame) để phát triển sau.

## 2. Kết quả (Deliverables)

Đã hoàn thành đầy đủ các bài nộp theo yêu cầu của Tuần 3:

*   [UX_PROTOTYPE.md](file:///c:/Users/Admin/Documents/CODE_WORKSPACE/Softeng/UX_PROTOTYPE.md): Bản phân tích kiến trúc và cơ chế hoạt động của UI Prototype.
*   [REQUIREMENTS.md](file:///c:/Users/Admin/Documents/CODE_WORKSPACE/Softeng/REQUIREMENTS.md): Bản đặc tả yêu cầu người dùng kèm kịch bản BDD và phạm vi MVP.
*   [ai-logs/week-03.md](file:///c:/Users/Admin/Documents/CODE_WORKSPACE/Softeng/ai-logs/week-03.md): Nhật ký phát triển tuần 3.

## 3. Đánh giá

*   **Đánh giá:** Bản UI Prototype được chuẩn bị rất tốt, có cấu trúc module phân vùng rõ ràng và logic giả lập phong phú. Việc ghi chép chi tiết kiến trúc prototype và định dạng các kịch bản BDD giúp nhóm hiểu sâu sắc hơn về hành vi hệ thống, chuẩn bị đầy đủ nền tảng để bước vào Tuần 4 (viết GitHub Issues chi tiết và chuẩn bị Prompts cho Agent thực thi code).
