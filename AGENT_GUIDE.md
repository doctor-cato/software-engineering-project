# Hướng dẫn dành cho AI Agent (Agent Guide)

Tài liệu này định nghĩa các quy tắc cốt lõi để các AI Agent (Cursor, Antigravity, GitHub Copilot) tuân thủ khi thao tác với codebase và tài liệu của 3HD2Kcinema.

## 1. Triết lý phát triển (Development Philosophy)
- Code cần: Hiện đại, Sạch sẽ, Dạng module, Dễ đọc, Dễ mở rộng.
- TRÁNH (Avoid): Overengineering, trừu tượng hóa không cần thiết, quản lý state quá phức tạp, tối ưu hóa sớm (premature optimization), và tạo ra các file quá lớn.
- **Code dễ đọc quan trọng hơn code thông minh/rườm rà.**

## 2. Quy tắc Frontend
- *Nhóm chưa chốt công nghệ Frontend. (Sẽ bổ sung sau)*

## 3. Quy tắc Backend & Database
- *Nhóm chưa chốt công nghệ Backend và Database. (Sẽ bổ sung sau)*

## 4. Quy tắc cho Realtime Seat Booking (Quan trọng nhất!)
- Đây là tính năng sống còn. Cần ngăn chặn double booking và đồng bộ realtime chính xác.
- Hỗ trợ tính năng "Split & Lock" cho việc đặt vé nhóm.
- **Luôn tự động nhả (unlock) ghế** khi người dùng ngắt kết nối hoặc không thao tác.

## 5. Quy trình làm việc & Tài liệu (Workflow & Docs)
- **Đồng bộ tài liệu:** Khi có bất kỳ thay đổi nào về tính năng, AI phải tự động nhắc nhở hoặc thực hiện việc cập nhật các file tài liệu chuẩn. **LƯU Ý:** Chỉ đọc và chỉnh sửa các file `.md` trong thư mục `Docs/MD type/`. TUYỆT ĐỐI KHÔNG đọc hay cố gắng chỉnh sửa các file `.docx`.
- Các nhánh chính: `main`, `develop`.
- Quy ước Commit: Dùng các tiền tố `feat:`, `fix:`, `refactor:`, `docs:`, `chore:`.
