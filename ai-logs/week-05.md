# Tuần 5: Nhật ký AI

**Thời gian:** 2026-06-15
**Mục tiêu:** Thiết kế hệ thống, kiến trúc cơ sở dữ liệu và chi tiết luồng hoạt động của tính năng AI theo mô hình MVP.

## Công việc đã thực hiện cùng AI Agent (Antigravity)
1. **Thiết kế Kiến trúc (Architecture):** 
   - Yêu cầu AI vẽ sơ đồ Mermaid mô tả rõ luồng đi từ Client (ReactJS) -> API Gateway (ASP.NET Core) -> Database (MongoDB). 
   - Xác định được vị trí tích hợp module SignalR cho tính năng khóa ghế thời gian thực (Real-time).
   - Xác định được vị trí kết nối với LLM Provider (AI_Service nằm ở tầng Backend).
   - Đã tạo: `Docs/architecture.md`
   
2. **Thiết kế Database (Data Model):**
   - Agent đã hỗ trợ vẽ sơ đồ ER Diagram (bằng Mermaid) minh họa cho cơ sở dữ liệu MongoDB.
   - Thống nhất các Collection cơ bản (Users, Movies, Bookings, Showtimes, Theaters) và bổ sung collection `Reviews` để phục vụ riêng cho tính năng AI.
   - Đã tạo: `Docs/data-model.md`

3. **Thiết kế tính năng AI (AI Feature Design):**
   - Từ các đề xuất ở tuần trước, chốt chọn tính năng "Phân tích cảm xúc từ Review".
   - AI đã giúp viết file `AI_FEATURE_DESIGN.md` bám sát chặt chẽ template bắt buộc của học phần.
   - Làm rõ được rủi ro ảo giác (Hallucination), các vấn đề rò rỉ dữ liệu cá nhân (Privacy) và cách phòng tránh (Sanitize data trước khi gửi cho LLM).
   - Đã tạo: `AI_FEATURE_DESIGN.md`

## Các khó khăn / Xử lý
- Ban đầu nhóm chưa xác định được sẽ dùng tính năng AI nào an toàn cho MVP. Nhờ sự hỗ trợ của Agent bám sát tài liệu hướng dẫn (`10weeks.md`), nhóm đã loại bỏ các tính năng AI phức tạp và chọn tính năng Phân tích cảm xúc để dễ kiểm soát chất lượng đầu ra.
