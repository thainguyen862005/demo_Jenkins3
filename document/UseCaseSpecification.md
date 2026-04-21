# USE CASE SPECIFICATION
# Hệ thống quản lý quán cà phê

## 1. Mục đích
Tài liệu này mô tả chi tiết các use case chính của hệ thống quản lý quán cà phê, bao gồm actor, điều kiện tiên quyết, luồng chính, luồng thay thế và hậu điều kiện.

---

## UC-01: Đăng nhập

- **Mã Use Case:** UC-01
- **Tên Use Case:** Đăng nhập
- **Actor:** Quản lý, Nhân viên phục vụ, Thu ngân
- **Mục tiêu:** Cho phép người dùng truy cập vào hệ thống bằng tài khoản hợp lệ.
- **Điều kiện tiên quyết:** Người dùng đã được cấp tài khoản và mật khẩu.
- **Điều kiện hậu:** Người dùng được chuyển đến giao diện phù hợp với vai trò.

### Luồng chính
1. Người dùng mở màn hình đăng nhập.
2. Người dùng nhập tên đăng nhập và mật khẩu.
3. Người dùng nhấn nút đăng nhập.
4. Hệ thống kiểm tra thông tin tài khoản.
5. Hệ thống xác thực thành công.
6. Hệ thống chuyển người dùng đến trang chính theo vai trò.

### Luồng thay thế
- 4a. Nếu tên đăng nhập hoặc mật khẩu không đúng:
  1. Hệ thống hiển thị thông báo lỗi.
  2. Người dùng nhập lại thông tin.
- 2a. Nếu người dùng bỏ trống thông tin:
  1. Hệ thống yêu cầu nhập đầy đủ dữ liệu.

---

## UC-02: Quản lý bàn

- **Mã Use Case:** UC-02
- **Tên Use Case:** Quản lý bàn
- **Actor:** Quản lý
- **Mục tiêu:** Quản lý danh sách bàn và trạng thái bàn trong quán.
- **Điều kiện tiên quyết:** Quản lý đã đăng nhập thành công.
- **Điều kiện hậu:** Danh sách bàn được cập nhật trong hệ thống.

### Luồng chính
1. Quản lý chọn chức năng quản lý bàn.
2. Hệ thống hiển thị danh sách bàn hiện có.
3. Quản lý chọn thêm mới, chỉnh sửa hoặc xóa bàn.
4. Quản lý nhập hoặc chỉnh sửa thông tin bàn.
5. Hệ thống lưu thay đổi.
6. Hệ thống cập nhật danh sách bàn.

### Luồng thay thế
- 3a. Nếu bàn đang có order hoạt động:
  1. Hệ thống không cho phép xóa bàn.
  2. Hệ thống hiển thị thông báo phù hợp.
- 4a. Nếu dữ liệu không hợp lệ:
  1. Hệ thống yêu cầu nhập lại.

---

## UC-03: Xem danh sách bàn

- **Mã Use Case:** UC-03
- **Tên Use Case:** Xem danh sách bàn
- **Actor:** Quản lý, Nhân viên phục vụ
- **Mục tiêu:** Xem trạng thái hiện tại của các bàn trong quán.
- **Điều kiện tiên quyết:** Người dùng đã đăng nhập.
- **Điều kiện hậu:** Người dùng biết được trạng thái của từng bàn.

### Luồng chính
1. Người dùng chọn chức năng xem bàn.
2. Hệ thống hiển thị danh sách bàn.
3. Hệ thống hiển thị trạng thái từng bàn như: trống, đang phục vụ, chờ thanh toán.
4. Người dùng chọn bàn cần thao tác nếu cần.

### Luồng thay thế
- 2a. Nếu chưa có dữ liệu bàn:
  1. Hệ thống hiển thị danh sách rỗng.

---

## UC-04: Quản lý menu

- **Mã Use Case:** UC-04
- **Tên Use Case:** Quản lý menu
- **Actor:** Quản lý
- **Mục tiêu:** Quản lý danh sách món, giá bán và trạng thái món.
- **Điều kiện tiên quyết:** Quản lý đã đăng nhập.
- **Điều kiện hậu:** Thông tin menu được cập nhật.

### Luồng chính
1. Quản lý chọn chức năng quản lý menu.
2. Hệ thống hiển thị danh sách món.
3. Quản lý chọn thêm món mới hoặc chỉnh sửa món hiện có.
4. Quản lý nhập các thông tin: tên món, loại món, giá, trạng thái.
5. Hệ thống kiểm tra tính hợp lệ của dữ liệu.
6. Hệ thống lưu thông tin món.
7. Hệ thống cập nhật danh sách menu.

### Luồng thay thế
- 5a. Nếu giá món không hợp lệ:
  1. Hệ thống hiển thị lỗi.
  2. Quản lý nhập lại dữ liệu.
- 3a. Nếu quản lý chọn xóa món đang xuất hiện trong order đang hoạt động:
  1. Hệ thống từ chối thao tác hoặc yêu cầu chuyển trạng thái tạm ngừng bán.

---

## UC-05: Tạo order

- **Mã Use Case:** UC-05
- **Tên Use Case:** Tạo order
- **Actor:** Nhân viên phục vụ
- **Mục tiêu:** Tạo order cho khách tại một bàn cụ thể.
- **Điều kiện tiên quyết:** Nhân viên đã đăng nhập, bàn hợp lệ tồn tại trong hệ thống.
- **Điều kiện hậu:** Order mới được tạo và gắn với bàn tương ứng.

### Luồng chính
1. Nhân viên chọn bàn cần phục vụ.
2. Hệ thống hiển thị menu.
3. Nhân viên chọn món và số lượng.
4. Nhân viên xác nhận tạo order.
5. Hệ thống lưu order.
6. Hệ thống cập nhật trạng thái bàn thành "Đang phục vụ".
7. Hệ thống hiển thị chi tiết order.

### Luồng thay thế
- 2a. Nếu không còn món phù hợp:
  1. Hệ thống vẫn hiển thị menu còn bán.
- 3a. Nếu món được chọn đang tạm ngừng bán:
  1. Hệ thống không cho thêm món đó vào order.

---

## UC-06: Cập nhật order

- **Mã Use Case:** UC-06
- **Tên Use Case:** Cập nhật order
- **Actor:** Nhân viên phục vụ
- **Mục tiêu:** Thay đổi thông tin order khi khách gọi thêm món hoặc hủy món.
- **Điều kiện tiên quyết:** Đã tồn tại order hoạt động cho bàn.
- **Điều kiện hậu:** Order được cập nhật chính xác theo yêu cầu mới.

### Luồng chính
1. Nhân viên mở order của bàn.
2. Hệ thống hiển thị danh sách món hiện tại.
3. Nhân viên chọn thêm món, sửa số lượng hoặc xóa món.
4. Hệ thống kiểm tra tính hợp lệ của thao tác.
5. Hệ thống cập nhật order.
6. Hệ thống tính lại tổng tiền tạm thời.
7. Hệ thống hiển thị order sau khi cập nhật.

### Luồng thay thế
- 3a. Nếu số lượng món nhập không hợp lệ:
  1. Hệ thống hiển thị lỗi.
- 3b. Nếu món đã bị tạm ngừng bán:
  1. Hệ thống không cho thêm món mới đó vào order.
- 3c. Nếu xóa toàn bộ món:
  1. Hệ thống có thể giữ order rỗng hoặc yêu cầu hủy order, tùy quy tắc nghiệp vụ.

---

## UC-07: Thanh toán hóa đơn

- **Mã Use Case:** UC-07
- **Tên Use Case:** Thanh toán hóa đơn
- **Actor:** Thu ngân
- **Mục tiêu:** Hoàn tất thanh toán cho một order.
- **Điều kiện tiên quyết:** Order đã tồn tại và chưa thanh toán.
- **Điều kiện hậu:** Hóa đơn được thanh toán thành công, trạng thái bàn trở về trống.

### Luồng chính
1. Thu ngân chọn hóa đơn cần thanh toán.
2. Hệ thống hiển thị thông tin order và tổng tiền.
3. Thu ngân chọn phương thức thanh toán.
4. Thu ngân xác nhận thanh toán.
5. Hệ thống ghi nhận giao dịch thanh toán.
6. Hệ thống cập nhật trạng thái order thành "Đã thanh toán".
7. Hệ thống cập nhật trạng thái bàn thành "Trống".
8. Hệ thống lưu hóa đơn vào lịch sử.

### Luồng thay thế
- 2a. Nếu hóa đơn không tồn tại:
  1. Hệ thống thông báo lỗi.
- 3a. Nếu phương thức thanh toán không hợp lệ:
  1. Hệ thống yêu cầu chọn lại.
- 4a. Nếu thu ngân hủy thao tác:
  1. Hệ thống không lưu thanh toán.

---

## UC-08: Quản lý nhân viên

- **Mã Use Case:** UC-08
- **Tên Use Case:** Quản lý nhân viên
- **Actor:** Quản lý
- **Mục tiêu:** Quản lý tài khoản người dùng trong hệ thống.
- **Điều kiện tiên quyết:** Quản lý đã đăng nhập.
- **Điều kiện hậu:** Thông tin nhân viên được cập nhật.

### Luồng chính
1. Quản lý chọn chức năng quản lý nhân viên.
2. Hệ thống hiển thị danh sách tài khoản.
3. Quản lý chọn thêm mới hoặc chỉnh sửa tài khoản.
4. Quản lý nhập thông tin nhân viên và vai trò.
5. Hệ thống kiểm tra dữ liệu.
6. Hệ thống lưu tài khoản.
7. Hệ thống cập nhật danh sách nhân viên.

### Luồng thay thế
- 4a. Nếu tên đăng nhập đã tồn tại:
  1. Hệ thống báo lỗi.
  2. Quản lý nhập lại thông tin.

---

## UC-09: Xem báo cáo doanh thu

- **Mã Use Case:** UC-09
- **Tên Use Case:** Xem báo cáo doanh thu
- **Actor:** Quản lý
- **Mục tiêu:** Theo dõi doanh thu của quán theo khoảng thời gian.
- **Điều kiện tiên quyết:** Quản lý đã đăng nhập và đã có dữ liệu hóa đơn thanh toán.
- **Điều kiện hậu:** Báo cáo doanh thu được hiển thị.

### Luồng chính
1. Quản lý chọn chức năng báo cáo doanh thu.
2. Quản lý chọn khoảng thời gian cần xem.
3. Hệ thống truy xuất dữ liệu hóa đơn đã thanh toán.
4. Hệ thống tính toán tổng doanh thu.
5. Hệ thống hiển thị kết quả báo cáo.
6. Hệ thống có thể hiển thị thêm số hóa đơn và món bán chạy.

### Luồng thay thế
- 3a. Nếu không có dữ liệu trong khoảng thời gian đã chọn:
  1. Hệ thống hiển thị doanh thu bằng 0 hoặc danh sách trống.

---

## UC-10: Tra cứu lịch sử hóa đơn

- **Mã Use Case:** UC-10
- **Tên Use Case:** Tra cứu lịch sử hóa đơn
- **Actor:** Thu ngân, Quản lý
- **Mục tiêu:** Tìm kiếm và xem lại hóa đơn đã thanh toán.
- **Điều kiện tiên quyết:** Người dùng đã đăng nhập.
- **Điều kiện hậu:** Hóa đơn cần tra cứu được hiển thị nếu tồn tại.

### Luồng chính
1. Người dùng chọn chức năng tra cứu lịch sử hóa đơn.
2. Người dùng nhập tiêu chí tìm kiếm như ngày, mã hóa đơn hoặc bàn.
3. Hệ thống truy xuất dữ liệu phù hợp.
4. Hệ thống hiển thị danh sách hóa đơn.
5. Người dùng chọn một hóa đơn để xem chi tiết.
6. Hệ thống hiển thị đầy đủ thông tin hóa đơn.

### Luồng thay thế
- 3a. Nếu không tìm thấy kết quả:
  1. Hệ thống hiển thị thông báo không có dữ liệu phù hợp.

---

## 2. Kết luận
Tài liệu Use Case Specification này mô tả chi tiết các chức năng nghiệp vụ cốt lõi của hệ thống quản lý quán cà phê.  
Đây là cơ sở trực tiếp để xây dựng SRS, thiết kế giao diện, thiết kế cơ sở dữ liệu và viết test case.
