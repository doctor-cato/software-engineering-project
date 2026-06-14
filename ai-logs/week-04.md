# Nhật ký Phát triển - Tuần 4 (Week 04)

**Giai đoạn:** Requirements, Issues và Agent-ready tasks

## 1. Các hoạt động đã thực hiện

*   **Tinh chỉnh và mở rộng User Stories:**
    *   Khảo sát và tích hợp các tính năng (features) từ bản mẫu UI Prototype (`web-application-development`) vào danh sách User Stories chính thức của dự án.
    *   Mở rộng từ 6 User Stories ban đầu lên tổng cộng 12 User Stories, bao phủ toàn diện các luồng nghiệp vụ (Tìm kiếm nâng cao, Bản đồ rạp, Hồ sơ cá nhân).
*   **Xác định AI User Stories:**
    *   Đã chọn và bổ sung 2 tính năng AI cụ thể: **US11 (AI Gợi ý phim & Cine-Match)** và **US12 (AI Tóm tắt đánh giá phim)**. Các tính năng này được thiết kế theo đúng triết lý "có kiểm soát rủi ro" và "nhỏ, gọn, giá trị cao" (Small, Controlled AI features).
*   **Chuyển đổi thành GitHub Issues:**
    *   Rà soát các GitHub Issues hiện tại (US01 đến US06).
    *   Tự động hóa việc tạo thêm các GitHub Issues mới (US08 đến US12) thông qua GitHub CLI, sẵn sàng cho việc phân công task cho Agent.
*   **Chuẩn bị Prompts (Agent-ready tasks):**
    *   Xây dựng tài liệu `PROMPTS.md` chứa các prompt mẫu kỹ thuật cao, hướng dẫn AI Agent cụ thể về role, context, và giới hạn công nghệ (constraints) để đảm bảo chất lượng code đầu ra.

## 2. Kết quả (Deliverables)

Đã hoàn thành các bài nộp theo yêu cầu của Tuần 4:

*   [REQUIREMENTS.md](../REQUIREMENTS.md): Danh sách cập nhật 12 User Stories, kèm Acceptance Criteria BDD và định nghĩa phạm vi MVP.
*   **GitHub Issues**: Đã tạo đầy đủ các issues trên GitHub Repository của dự án.
*   [PROMPTS.md](../PROMPTS.md): Bộ template prompt chuẩn mực tối ưu cho việc giao tiếp với AI.
*   [week-04.md](./week-04.md): Nhật ký báo cáo tiến độ tuần 4.

## 3. Đánh giá

*   **Đánh giá:** Việc chuyển từ User Story sang GitHub Issue với các Acceptance Criteria rõ ràng giúp phân mảnh dự án rất tốt. AI Agent có thể dễ dàng tiếp nhận các issue này (Ví dụ: thông qua lệnh `@agent implement Issue #12`) mà không bị quá tải thông tin, hạn chế tối đa tình trạng ảo giác (hallucination) khi viết code cũng như ngăn chặn over-engineering.
