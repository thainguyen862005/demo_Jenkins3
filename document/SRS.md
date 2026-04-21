# SOFTWARE REQUIREMENTS SPECIFICATION (SRS)
# Hệ thống quản lý quán cà phê

---

## 1. Thông tin tài liệu

| Mục | Nội dung |
|---|---|
| Tên dự án | Hệ thống quản lý quán cà phê |
| Tên tiếng Anh | Coffee Shop Management System |
| Loại tài liệu | Software Requirements Specification |
| Phiên bản | 1.0 |
| Ngày cập nhật | [Điền ngày] |
| Nhóm thực hiện | [Điền tên nhóm] |
| Môn học | Công nghệ phần mềm |
| Giảng viên hướng dẫn | [Điền tên giảng viên] |

---

## 2. Mục đích tài liệu

Tài liệu này mô tả các yêu cầu phần mềm cho hệ thống quản lý quán cà phê.  
Mục tiêu của tài liệu là:

- Xác định rõ các chức năng mà hệ thống phải cung cấp.
- Xác định các yêu cầu phi chức năng và ràng buộc kỹ thuật.
- Làm cơ sở cho thiết kế hệ thống, lập trình, kiểm thử và nghiệm thu.
- Đảm bảo các thành viên trong nhóm hiểu thống nhất về phạm vi và cách hoạt động của hệ thống.

---

## 3. Phạm vi hệ thống

Hệ thống quản lý quán cà phê là một ứng dụng hỗ trợ số hóa hoạt động vận hành của quán, bao gồm:

- quản lý bàn
- quản lý menu
- tạo và cập nhật order
- thanh toán hóa đơn
- quản lý tài khoản nhân viên
- theo dõi doanh thu
- tra cứu lịch sử hóa đơn

Hệ thống phục vụ cho các nhóm người dùng chính:

- Quản lý
- Nhân viên phục vụ
- Thu ngân

Trong phiên bản hiện tại, hệ thống không bao gồm:

- thanh toán online thực tế
- quản lý kho nguyên liệu chi tiết
- đặt bàn trực tuyến
- tích điểm khách hàng thân thiết
- quản lý nhiều chi nhánh

---

## 4. Định nghĩa và từ viết tắt

| Thuật ngữ | Giải thích |
|---|---|
| Actor | Người dùng hoặc vai trò tương tác với hệ thống |
| Menu | Danh sách món ăn, đồ uống mà quán đang kinh doanh |
| Order | Danh sách món mà khách hàng gọi tại một bàn |
| Hóa đơn | Kết quả thanh toán của một order |
| SRS | Software Requirements Specification |
| BRD | Business Requirements Document |
| FR | Functional Requirement |
| NFR | Non-functional Requirement |

---

## 5. Mô tả tổng quan

### 5.1. Bối cảnh hệ thống
Nhiều quán cà phê nhỏ hiện vẫn ghi order và tính tiền thủ công, dễ dẫn đến nhầm món, nhầm bàn, sai tổng tiền và khó theo dõi doanh thu. Hệ thống này được xây dựng để hỗ trợ quản lý các nghiệp vụ đó trên cùng một nền tảng.

### 5.2. Mục tiêu hệ thống
- Giảm sai sót khi nhận món và thanh toán
- Tăng tốc độ phục vụ khách hàng
- Hỗ trợ quản lý tập trung menu, bàn và nhân viên
- Cung cấp báo cáo doanh thu cơ bản
- Tạo nền tảng mở rộng trong tương lai

### 5.3. Các nhóm người dùng

#### Quản lý
- quản lý bàn
- quản lý menu
- quản lý nhân viên
- xem báo cáo doanh thu
- tra cứu lịch sử hóa đơn

#### Nhân viên phục vụ
- xem danh sách bàn
- tạo order
- cập nhật order

#### Thu ngân
- thanh toán hóa đơn
- tra cứu lịch sử hóa đơn

### 5.4. Giả định
- Mỗi người dùng có tài khoản riêng để đăng nhập.
- Mỗi bàn tại một thời điểm chỉ có một order đang hoạt động.
- Các món trong menu có trạng thái còn bán hoặc tạm ngừng bán.
- Quán có kết nối hệ thống ổn định trong quá trình vận hành.

### 5.5. Ràng buộc
- Hệ thống được phát triển trong phạm vi đồ án môn học.
- Chưa tích hợp thiết bị phần cứng thật như máy in hóa đơn hoặc máy POS.
- Một số chức năng nâng cao sẽ không nằm trong phiên bản đầu tiên.

---

## 6. Yêu cầu chức năng

### FR-01: Đăng nhập

**Mô tả:**  
Hệ thống cho phép người dùng đăng nhập bằng tên đăng nhập và mật khẩu.

**Đầu vào:**  
- Tên đăng nhập
- Mật khẩu

**Xử lý:**  
- Kiểm tra dữ liệu nhập vào
- Đối chiếu thông tin tài khoản trong cơ sở dữ liệu
- Xác định vai trò người dùng

**Đầu ra:**  
- Đăng nhập thành công và chuyển đến giao diện chính
- Hoặc thông báo lỗi nếu thông tin không hợp lệ

**Điều kiện chấp nhận:**  
- Người dùng hợp lệ đăng nhập được
- Người dùng không hợp lệ không thể truy cập hệ thống

---

### FR-02: Quản lý bàn

**Mô tả:**  
Hệ thống cho phép quản lý thêm, sửa, xóa và cập nhật trạng thái bàn.

**Actor:**  
Quản lý

**Đầu vào:**  
- Mã bàn
- Tên bàn hoặc số bàn
- Trạng thái bàn

**Xử lý:**  
- Kiểm tra tính hợp lệ dữ liệu
- Lưu hoặc cập nhật thông tin bàn
- Từ chối xóa bàn nếu bàn đang có order hoạt động

**Đầu ra:**  
- Danh sách bàn được cập nhật

**Điều kiện chấp nhận:**  
- Thêm bàn thành công khi dữ liệu hợp lệ
- Không cho xóa bàn nếu đang được sử dụng

---

### FR-03: Xem danh sách bàn

**Mô tả:**  
Hệ thống cho phép người dùng xem danh sách bàn và trạng thái hiện tại của từng bàn.

**Actor:**  
Quản lý, Nhân viên phục vụ

**Đầu vào:**  
- Yêu cầu xem danh sách bàn

**Xử lý:**  
- Truy xuất danh sách bàn từ hệ thống
- Hiển thị trạng thái từng bàn

**Đầu ra:**  
- Danh sách bàn
- Trạng thái: Trống, Đang phục vụ, Chờ thanh toán

**Điều kiện chấp nhận:**  
- Hệ thống hiển thị đúng trạng thái của từng bàn

---

### FR-04: Quản lý menu

**Mô tả:**  
Hệ thống cho phép quản lý thêm, sửa, xóa và cập nhật món trong menu.

**Actor:**  
Quản lý

**Đầu vào:**  
- Tên món
- Loại món
- Giá bán
- Mô tả
- Trạng thái món

**Xử lý:**  
- Kiểm tra dữ liệu món
- Lưu thông tin món vào hệ thống
- Không cho phép nhập giá âm hoặc dữ liệu không hợp lệ

**Đầu ra:**  
- Danh sách món được cập nhật

**Điều kiện chấp nhận:**  
- Có thể thêm món mới
- Có thể sửa thông tin món
- Món tạm ngừng bán không được thêm vào order mới

---

### FR-05: Tạo order

**Mô tả:**  
Hệ thống cho phép nhân viên phục vụ tạo order cho một bàn cụ thể.

**Actor:**  
Nhân viên phục vụ

**Đầu vào:**  
- Bàn được chọn
- Danh sách món
- Số lượng từng món

**Xử lý:**  
- Kiểm tra bàn hợp lệ
- Hiển thị các món còn bán
- Tạo order mới
- Gắn order với bàn
- Cập nhật trạng thái bàn

**Đầu ra:**  
- Order mới được tạo
- Bàn chuyển sang trạng thái "Đang phục vụ"

**Điều kiện chấp nhận:**  
- Tạo order thành công khi bàn hợp lệ và món hợp lệ
- Không cho thêm món đang tạm ngừng bán

---

### FR-06: Cập nhật order

**Mô tả:**  
Hệ thống cho phép nhân viên cập nhật order trong quá trình phục vụ.

**Actor:**  
Nhân viên phục vụ

**Đầu vào:**  
- Mã order
- Danh sách món cần thêm, sửa hoặc xóa

**Xử lý:**  
- Kiểm tra order đang hoạt động
- Cập nhật danh sách món
- Tính lại tổng tiền tạm thời

**Đầu ra:**  
- Order được cập nhật
- Tổng tiền tạm thời được thay đổi tương ứng

**Điều kiện chấp nhận:**  
- Có thể thêm món mới
- Có thể sửa số lượng món
- Có thể xóa món khỏi order trước khi thanh toán

---

### FR-07: Thanh toán hóa đơn

**Mô tả:**  
Hệ thống cho phép thu ngân thực hiện thanh toán cho order.

**Actor:**  
Thu ngân

**Đầu vào:**  
- Mã order hoặc hóa đơn
- Phương thức thanh toán

**Xử lý:**  
- Hiển thị thông tin chi tiết order
- Tính tổng tiền
- Ghi nhận phương thức thanh toán
- Cập nhật trạng thái order và bàn
- Lưu lịch sử thanh toán

**Đầu ra:**  
- Hóa đơn được thanh toán thành công
- Bàn chuyển về trạng thái "Trống"

**Điều kiện chấp nhận:**  
- Tổng tiền được tính chính xác
- Sau thanh toán, order chuyển sang trạng thái đã thanh toán
- Bàn được cập nhật về trống

---

### FR-08: Quản lý nhân viên

**Mô tả:**  
Hệ thống cho phép quản lý thêm, sửa và quản lý tài khoản nhân viên.

**Actor:**  
Quản lý

**Đầu vào:**  
- Họ tên nhân viên
- Tên đăng nhập
- Mật khẩu
- Vai trò
- Trạng thái tài khoản

**Xử lý:**  
- Kiểm tra dữ liệu
- Kiểm tra trùng tên đăng nhập
- Tạo hoặc cập nhật tài khoản nhân viên

**Đầu ra:**  
- Danh sách nhân viên được cập nhật

**Điều kiện chấp nhận:**  
- Không cho phép tạo 2 tài khoản trùng tên đăng nhập
- Chỉ quản lý mới có quyền thao tác chức năng này

---

### FR-09: Xem báo cáo doanh thu

**Mô tả:**  
Hệ thống cho phép quản lý xem báo cáo doanh thu theo thời gian.

**Actor:**  
Quản lý

**Đầu vào:**  
- Ngày
- Tháng
- Khoảng thời gian tùy chọn

**Xử lý:**  
- Lấy dữ liệu từ các hóa đơn đã thanh toán
- Tính tổng doanh thu
- Thống kê số hóa đơn và món bán chạy nếu có

**Đầu ra:**  
- Báo cáo doanh thu theo yêu cầu

**Điều kiện chấp nhận:**  
- Báo cáo phản ánh đúng dữ liệu từ hóa đơn đã thanh toán
- Hiển thị được doanh thu theo khoảng thời gian đã chọn

---

### FR-10: Tra cứu lịch sử hóa đơn

**Mô tả:**  
Hệ thống cho phép người dùng tra cứu các hóa đơn đã thanh toán.

**Actor:**  
Quản lý, Thu ngân

**Đầu vào:**  
- Ngày
- Mã hóa đơn
- Bàn
- Khoảng thời gian

**Xử lý:**  
- Tìm kiếm hóa đơn trong hệ thống
- Hiển thị danh sách kết quả phù hợp
- Cho phép xem chi tiết hóa đơn

**Đầu ra:**  
- Danh sách hóa đơn tìm được
- Thông tin chi tiết hóa đơn

**Điều kiện chấp nhận:**  
- Có thể tìm hóa đơn theo các tiêu chí cơ bản
- Nếu không có kết quả, hệ thống hiển thị thông báo phù hợp

---

## 7. Yêu cầu phi chức năng

### NFR-01: Hiệu năng
- Hệ thống phải phản hồi các thao tác thông thường trong thời gian hợp lý.
- Thời gian xử lý các chức năng chính nên nhỏ hơn 3 giây trong điều kiện sử dụng bình thường.

### NFR-02: Tính dễ sử dụng
- Giao diện phải rõ ràng, dễ thao tác đối với người dùng phổ thông.
- Các chức năng nhận order và thanh toán phải trực quan, ít bước thao tác.

### NFR-03: Bảo mật
- Người dùng phải đăng nhập trước khi sử dụng hệ thống.
- Mật khẩu phải được lưu trữ an toàn.
- Chức năng phải được phân quyền theo vai trò.

### NFR-04: Tính ổn định
- Hệ thống phải hoạt động ổn định trong quá trình sử dụng thông thường.
- Dữ liệu không được mất khi người dùng thực hiện các thao tác hợp lệ.

### NFR-05: Khả năng mở rộng
- Hệ thống cần cho phép mở rộng trong tương lai như:
  - quản lý kho
  - đặt bàn online
  - quản lý khách hàng thân thiết
  - thanh toán điện tử

### NFR-06: Khả năng bảo trì
- Mã nguồn phải được tổ chức rõ ràng.
- Dễ sửa lỗi và nâng cấp hệ thống.
- Các thành phần backend, frontend và database nên được tách biệt.

---

## 8. Business Rules

- Mỗi bàn tại một thời điểm chỉ có một order đang hoạt động.
- Chỉ quản lý mới được thêm, sửa, xóa menu và quản lý nhân viên.
- Chỉ thu ngân mới được xác nhận thanh toán hóa đơn.
- Món ở trạng thái "Tạm ngừng bán" không được thêm vào order.
- Doanh thu chỉ được tính từ các hóa đơn đã thanh toán thành công.
- Sau khi thanh toán xong, trạng thái bàn phải chuyển về "Trống".
- Tên đăng nhập của mỗi nhân viên phải là duy nhất.
- Không được xóa bàn nếu bàn đang có order hoạt động.

---

## 9. Use Case liên quan

| Mã Use Case | Tên Use Case | Yêu cầu chức năng liên quan |
|---|---|---|
| UC-01 | Đăng nhập | FR-01 |
| UC-02 | Quản lý bàn | FR-02 |
| UC-03 | Xem danh sách bàn | FR-03 |
| UC-04 | Quản lý menu | FR-04 |
| UC-05 | Tạo order | FR-05 |
| UC-06 | Cập nhật order | FR-06 |
| UC-07 | Thanh toán hóa đơn | FR-07 |
| UC-08 | Quản lý nhân viên | FR-08 |
| UC-09 | Xem báo cáo doanh thu | FR-09 |
| UC-10 | Tra cứu lịch sử hóa đơn | FR-10 |

---

## 10. Ràng buộc giao diện

Hệ thống cần có tối thiểu các màn hình sau:

- Màn hình đăng nhập
- Màn hình danh sách bàn
- Màn hình quản lý menu
- Màn hình tạo và cập nhật order
- Màn hình thanh toán hóa đơn
- Màn hình quản lý nhân viên
- Màn hình báo cáo doanh thu
- Màn hình tra cứu lịch sử hóa đơn

---

## 11. Ràng buộc dữ liệu

Hệ thống cần có các thực thể dữ liệu cơ bản sau:

- User
- Role
- Table
- Category
- Product
- Order
- OrderItem
- Payment

### Quan hệ dữ liệu cơ bản
- Một Role có nhiều User
- Một Table có nhiều Order theo thời gian
- Một Order có nhiều OrderItem
- Một Product có thể xuất hiện trong nhiều OrderItem
- Một Order gắn với một Payment sau khi thanh toán

---

## 12. Tiêu chí chấp nhận hệ thống

Hệ thống được xem là đạt yêu cầu khi:

1. Người dùng đăng nhập được đúng với vai trò đã cấp.
2. Quản lý được bàn, menu và nhân viên.
3. Nhân viên phục vụ có thể tạo và cập nhật order.
4. Thu ngân có thể thanh toán hóa đơn chính xác.
5. Sau khi thanh toán, bàn được cập nhật về trạng thái trống.
6. Quản lý xem được báo cáo doanh thu cơ bản.
7. Người dùng có thể tra cứu lịch sử hóa đơn.
8. Hệ thống hoạt động ổn định trong các luồng nghiệp vụ chính.

---

## 13. Ma trận truy vết yêu cầu

| Mã yêu cầu | Nguồn gốc | Use Case | Kiểm thử dự kiến |
|---|---|---|---|
| FR-01 | BRD | UC-01 | TC-01, TC-02, TC-03 |
| FR-02 | BRD | UC-02 | TC-04, TC-05, TC-06 |
| FR-03 | BRD | UC-03 | TC-07 |
| FR-04 | BRD | UC-04 | TC-08, TC-09, TC-10 |
| FR-05 | BRD | UC-05 | TC-11, TC-12 |
| FR-06 | BRD | UC-06 | TC-13, TC-14 |
| FR-07 | BRD | UC-07 | TC-15, TC-16 |
| FR-08 | BRD | UC-08 | TC-17, TC-18 |
| FR-09 | BRD | UC-09 | TC-19 |
| FR-10 | BRD | UC-10 | TC-20 |

---

## 14. Kết luận

Tài liệu SRS này mô tả chi tiết các yêu cầu phần mềm của hệ thống quản lý quán cà phê.  
Đây là cơ sở để nhóm thực hiện các bước tiếp theo gồm:

- thiết kế Activity Diagram
- thiết kế Sequence Diagram
- thiết kế Class Diagram
- thiết kế ERD
- lập kế hoạch kiểm thử
- xây dựng test case
- triển khai và hoàn thiện hệ thống
