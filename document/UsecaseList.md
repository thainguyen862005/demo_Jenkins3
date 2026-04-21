# USE CASE LIST
# Hệ thống quản lý quán cà phê

## 1. Mục đích
Tài liệu này liệt kê các actor và các use case chính của hệ thống quản lý quán cà phê.  
Danh sách này được trích xuất từ Business Requirements Document (BRD) và là cơ sở để xây dựng Use Case Diagram, Use Case Specification, SRS và các tài liệu thiết kế khác.

---

## 2. Actors

### 2.1. Quản lý
Người chịu trách nhiệm quản lý hoạt động chung của quán, bao gồm quản lý bàn, menu, nhân viên và theo dõi báo cáo doanh thu.

### 2.2. Nhân viên phục vụ
Người trực tiếp nhận order từ khách, tạo order, cập nhật order và theo dõi trạng thái bàn.

### 2.3. Thu ngân
Người chịu trách nhiệm xử lý thanh toán, in/xuất hóa đơn và tra cứu lịch sử hóa đơn.

---

## 3. Danh sách Use Case

| Mã Use Case | Tên Use Case | Actor chính | Mô tả ngắn |
|---|---|---|---|
| UC-01 | Đăng nhập | Quản lý, Nhân viên phục vụ, Thu ngân | Người dùng đăng nhập vào hệ thống bằng tài khoản hợp lệ |
| UC-02 | Quản lý bàn | Quản lý | Thêm, sửa, xóa hoặc cập nhật trạng thái bàn |
| UC-03 | Xem danh sách bàn | Nhân viên phục vụ, Quản lý | Xem danh sách bàn và trạng thái hiện tại của từng bàn |
| UC-04 | Quản lý menu | Quản lý | Thêm, sửa, xóa món và cập nhật thông tin món |
| UC-05 | Tạo order | Nhân viên phục vụ | Tạo order cho một bàn cụ thể |
| UC-06 | Cập nhật order | Nhân viên phục vụ | Thêm món, sửa số lượng hoặc xóa món trong order |
| UC-07 | Thanh toán hóa đơn | Thu ngân | Xác nhận thanh toán cho order đã hoàn tất |
| UC-08 | Quản lý nhân viên | Quản lý | Quản lý tài khoản và vai trò nhân viên |
| UC-09 | Xem báo cáo doanh thu | Quản lý | Xem báo cáo doanh thu theo ngày, tháng hoặc khoảng thời gian |
| UC-10 | Tra cứu lịch sử hóa đơn | Thu ngân, Quản lý | Tìm kiếm và xem lại các hóa đơn đã thanh toán |

---

## 4. Phân rã Use Case theo Actor

### 4.1. Quản lý
- UC-01: Đăng nhập
- UC-02: Quản lý bàn
- UC-03: Xem danh sách bàn
- UC-04: Quản lý menu
- UC-08: Quản lý nhân viên
- UC-09: Xem báo cáo doanh thu
- UC-10: Tra cứu lịch sử hóa đơn

### 4.2. Nhân viên phục vụ
- UC-01: Đăng nhập
- UC-03: Xem danh sách bàn
- UC-05: Tạo order
- UC-06: Cập nhật order

### 4.3. Thu ngân
- UC-01: Đăng nhập
- UC-07: Thanh toán hóa đơn
- UC-10: Tra cứu lịch sử hóa đơn

---

## 5. Ghi chú phạm vi
Trong phiên bản hiện tại, hệ thống chưa bao gồm các use case nâng cao như:
- Đặt bàn online
- Quét QR để khách tự order
- Thanh toán online thật
- Quản lý kho nguyên liệu chi tiết
- Tích điểm khách hàng thân thiết

Các chức năng trên có thể được xem là hướng mở rộng trong tương lai.

---

## 6. Kết luận
Danh sách use case trên phản ánh các chức năng cốt lõi của hệ thống quản lý quán cà phê trong phạm vi đồ án môn Công nghệ phần mềm.  
Tài liệu này là cơ sở để xây dựng sơ đồ Use Case, đặc tả Use Case và tài liệu SRS ở các bước tiếp theo.
