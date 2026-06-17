# Kiến trúc Phần mềm 3HD2Kcinema

## 1. Tầm quan trọng của Kiến trúc phần mềm 3HD2Kcinema
Kiến trúc quyết định chất lượng phi chức năng của hệ thống rạp phim:
- **Hiệu suất (Performance):** Tối ưu hóa tốc độ tra cứu lịch chiếu phim và sơ đồ ghế bằng cách tách biệt luồng đọc dữ liệu thô (Queries).
- **Bảo mật (Security):** Kiểm soát nghiêm ngặt quyền truy cập API bằng bộ lọc Middleware xác thực trước khi request tới Controllers.
- **Tính bảo trì (Maintainability):** Tổ chức mã nguồn phân tầng rõ ràng, giúp dễ dàng thêm chức năng mới (như quản lý combo bắp nước) mà không làm ảnh hưởng phần đặt vé cốt lõi.
## 2. Các Đánh đổi trong Kiến trúc 3HD2Kcinema
**Bảo mật dữ liệu với Trải nghiệm người dùng:**
- Mã hóa dữ liệu và ẩn thông tin nhạy cảm.
- Giải pháp: Sử dụng hệ thống các lớp DTOs (như `MovieResponseDto`, `BookingResponseDto`) để chỉ trả về những dữ liệu giao diện cần, giấu hoàn toàn các thông tin cấu trúc cơ sở dữ liệu gốc của hệ thống.

## 3. Mô hình Triển khai Client - Server 3 Tầng
Hệ thống áp dụng mô hình kiến trúc phân tầng truyền thống nhưng triển khai tinh gọn:
- **Client Layer:** Trình duyệt phía người dùng, hiển thị giao diện thông qua tầng Views (Razor Pages) được render từ máy chủ.
- **Application Server (ASP.NET Core Web App):** Dự án appweb chịu trách nhiệm xử lý toàn bộ yêu cầu, điều hướng thông qua Controllers và xử lý logic đặt vé tại Services.
- **Database Server (SQL Server):** Lưu trữ dữ liệu tập trung thông qua sự quản lý của Entity Framework Core (`ApplicationDbContext`).

## 4. Kiến trúc Phân tầng của hệ thống
- **Tầng Giao diện & Điều hướng (Presentation):** Views & Controllers (Tiếp nhận request từ khách hàng, hiển thị sơ đồ ghế, lịch chiếu).
- **Tầng Trung chuyển Dữ liệu:** DTOs (Bao bọc và bảo mật dữ liệu truyền nhận giữa các tầng).
- **Tầng Logic Nghiệp vụ (Business Logic):** Services (`BookingService`, `OrderService` - Nơi tính tiền vé, xác thực vé).
- **Tầng Truy cập dữ liệu (Data Access Layer):** Repositories & Queries (Trừu tượng hóa các câu lệnh SQL, thực hiện CRUD dữ liệu phim, rạp).
- **Tầng Hạ tầng & CSDL (Infrastructure):** Models & `ApplicationDbContext` (Định nghĩa bảng và kết nối Database).

## 5. Công nghệ Hiện thực hóa Kiến trúc
- **Framework cốt lõi:** ASP.NET Core MVC (C#) – Đảm bảo hiệu năng cao, bảo mật tốt cho hệ thống backend web.
- **Cơ sở dữ liệu (Database):** Relational Database (SQL Server) – Bắt buộc phải dùng vì hệ thống rạp phim yêu cầu quản lý giao dịch khắt khe (Transaction), đảm bảo tính toàn vẹn khi khóa ghế, tránh tình trạng hai người đặt trùng một ghế cùng một lúc.
- **ORM (Hạ tầng kết nối):** Entity Framework Core thông qua `ApplicationDbContext` – Giúp ánh xạ các lớp Models thành bảng CSDL tự động, tăng tốc độ viết code xử lý.

## 6. Các nguyên tắc thiết kế và mẫu định dạng
- **Separation of Concerns (Phân tách mối bận tâm):** Tách biệt tầng dữ liệu và tầng nghiệp vụ. `BookingService` chỉ lo tính logic đặt vé, không cần quan tâm Database phía dưới là SQL hay NoSQL nhờ có `BookingRepository` làm trung gian che giấu.
- **Implement Once (Triển khai một lần):** Các service dùng chung như `TicketVerificationService` (Xác thực vé) được viết một lần và có thể gọi ở cả luồng kiểm tra tại quầy lẫn luồng đặt online.
- **Loosely Coupled (Giảm độ phụ thuộc chéo):** Controllers không gọi trực tiếp xuống Database mà phải đi qua tầng trung gian, giúp dễ dàng kiểm thử độc lập (Unit Test).
