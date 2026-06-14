# Hướng dẫn Git Workflow dành cho AI Agent (GIT_WORKFLOW_AI.md)

Tài liệu này đặc tả quy trình tương tác với Git và GitHub mà các AI Agent (Gemini Antigravity, Cursor, Claude Code, Cline, v.v.) **bắt buộc phải tuân thủ** khi thực hiện viết code, sửa lỗi hoặc cập nhật tài liệu trong dự án **3HD2Kcinema**.

---

## 1. Nguyên tắc cốt lõi (Core Principles)
*   **TUYỆT ĐỐI KHÔNG** commit trực tiếp lên nhánh `main` hoặc `develop`. Mọi thay đổi logic ứng dụng phải được thực hiện trên các nhánh tính năng (Feature Branch) riêng biệt.
*   **KHÔNG** gộp nhiều tính năng/sửa lỗi khác nhau vào cùng một nhánh hoặc một commit lớn. Hãy giữ các thay đổi nhỏ, tập trung và có tính nguyên tử (atomic changes).
*   **LUÔN** thực hiện đồng bộ nhánh làm việc với mã nguồn mới nhất từ remote trước khi tiến hành code.

---

## 2. Quy trình 5 bước dành cho AI Agent

### Bước 1: Khởi tạo và đồng bộ nhánh
Khi nhận lệnh thực hiện một Issue hoặc User Story (Ví dụ: `US03`):
1.  Chuyển về nhánh tích hợp chính (`develop` hoặc `main` tùy cấu hình dự án, hiện tại là `master` hoặc `develop` theo [CONTRIBUTING.md](file:///c:/Users/Admin/Documents/CODE_WORKSPACE/Softeng/CONTRIBUTING.md)).
2.  Kéo code mới nhất về:
    ```bash
    git checkout master
    git pull origin master
    ```
3.  Tạo nhánh mới tách từ nhánh chính theo quy ước đặt tên:
    *   Tính năng mới: `feature/usXX-ten-tinh-nang` (Ví dụ: `feature/us03-snack-booking`)
    *   Sửa lỗi: `bugfix/usXX-ten-loi` (Ví dụ: `bugfix/us02-seat-sync-error`)
    *   Tài liệu: `docs/week-XX-update`
    ```bash
    git checkout -b feature/us03-snack-booking
    ```

### Bước 2: Triển khai & Kiểm thử cục bộ
*   Thực hiện viết code hoặc cập nhật file theo kế hoạch đã được phê duyệt.
*   Sau khi sửa code, chạy các lệnh test tự động (nếu có) hoặc thực hiện các bước kiểm tra thủ công để đảm bảo code chạy đúng và không làm hỏng các tính năng cũ.

### Bước 3: Đóng gói commit (Commit Changes)
*   Sử dụng chuẩn **Conventional Commits** để viết thông điệp commit.
*   Định dạng commit bắt buộc: `<type>: <description>`
    *   `feat`: Tính năng mới (Ví dụ: `feat: add concessions screen to booking flow`)
    *   `fix`: Sửa lỗi (Ví dụ: `fix: correct seat unlock countdown expiration logic`)
    *   `docs`: Chỉ thay đổi tài liệu (Ví dụ: `docs: update AI git workflow guide`)
    *   `style`: Định dạng code, sửa CSS (không ảnh hưởng logic)
    *   `refactor`: Tái cấu trúc mã nguồn (Ví dụ: `refactor: move shared components to shared folder`)
*   *Lưu ý:* Phân tách rõ ràng các phần sửa đổi bằng nhiều commit nhỏ nếu cần thiết.

### Bước 4: Đẩy nhánh (Push to Remote)
Sau khi hoàn thành và tạo commit cục bộ, hãy đề xuất lệnh đẩy nhánh lên GitHub:
```bash
git push origin feature/us03-snack-booking
```

### Bước 5: Hướng dẫn tạo Pull Request (PR)
AI Agent sau khi push nhánh cần hiển thị thông báo hướng dẫn người dùng tạo Pull Request trên GitHub với các thông tin:
*   Tiêu đề PR rõ ràng.
*   Mô tả ngắn gọn các thay đổi đã thực hiện.
*   **Liên kết tự động đóng Issue:** Ghi rõ cú pháp `Closes #<Issue_ID>` (Ví dụ: `Closes #24`) để GitHub tự động đóng Issue tương ứng sau khi PR được merge.

---

## 3. Quy trình xử lý xung đột (Conflict Resolution)
Nếu xảy ra xung đột code (Merge Conflict) trong quá trình phát triển hoặc khi chuẩn bị merge:
1.  AI Agent phải kéo nhánh chính mới nhất về cục bộ.
2.  Trộn nhánh chính vào nhánh tính năng đang làm việc:
    ```bash
    git checkout master
    git pull origin master
    git checkout feature/us03-snack-booking
    git merge master
    ```
3.  Sử dụng công cụ đọc file để xác định các vùng bị xung đột (dấu hiệu `<<<<<<<`, `=======`, `>>>>>>>`).
4.  Giải quyết xung đột một cách cẩn thận, đảm bảo không xóa nhầm code hợp lệ của thành viên khác.
5.  Tạo commit xác nhận giải quyết xung đột và push lại lên remote.
