# Khái niệm CSS
### Khái niệm
- Cascading style sheets là tên full
- CSS là định dạng độc lập so với HTML, thiết lập mẫu định dạng dùng trong web
- Tập hợp những mẫu định dạng viết độc lập so với mã nguồn HTML
### Cấu trúc
- Hai phần
	**Bộ chọn** (selector)
	**Vùng miêu tả** (Declaration)
- CSS trong (internal): Sử dụng thẻ style trực tiếp trong thẻ head.
	![[Pasted image 20260316211732.png]]
- CSS ngoài (external): Dùng một tệp .css mở rộng bên ngoài rồi link lại với thẻ link vào file HTML. Hoặc dùng @import kẹp trong thẻ style, kẹp trong head, kết thúc bằng dấu ; . Link bao gồm:
	- href: tên file
	- rel = stylesheet (quan hệ)
	- type = text/css
	**EXTERNAL THÌ LUÔN PHẢI Ở TRONG THẺ HEAD, KHÔNG ĐỨNG MỘT MÌNH**
	![[Pasted image 20260316211804.png]]
	![[Pasted image 20260316211834.png]]
	![[Pasted image 20260316211844.png]]
- CSS nội tuyến (inline): Dùng thẻ style lồng vào trong các thuộc tính ở file HTML
	![[Pasted image 20260316211942.png]]
### Vai trò, ý nghĩa 
- Tách nhập nội dung và định dạng thành 2 việc độc lập
- Viết 1 lần, áp dụng, thay đổi nhiều lần
- Kết nối với bất kì trang web nào
# Định dạng văn bản bằng CSS
### Phông chữ
- Dùng **font-family** để chọn phông
	- Phân theo họ: serif (có chân), sans-serif (không có chân), monospace (dàn đều, **trong sách là có chân ở dưới**), cursive (viết tay, **trong sách là hơi tròn tròn**), fantasy (trừu tượng, **IMPACT**)
	- Có thể nhận giá trị là một danh sách các tên font, trình duyệt sẽ lựa qua và tìm cái hiển thị văn bản
	 ![[Pasted image 20260315231304.png]]
- Dùng **font-style** chọn kiểu chữ
	- Thiết lập in nghiêng hay in thường: nhận giá trị **normal** hay là **italics** 
- Dùng **font-size** chọn cỡ, nhận các giá trị:
	- Chinh xác: cm, mm, inch, px, pt
		- in (1 inch = 2.54 cm)
		- px (1 pixel = 1/96 inch)
		- pt (1 point = 1/72 inch)
	- Tương đối:
		- em: so với cỡ chữ **hiện thời** của trình duyệt - phần tử ở phía trước
		- ex: so với chiều cao chữ x của cỡ hiện thời - 
		- rem: so với cỡ của phần tử HTML gốc (**root**)
		- %: theo phần trăm của phần tử cha
		- Mức: xx-small, x-small, small, medium, x-large, xx-large, mặc định là medium
- Dùng **font-weight** chọn độ in đậm
	- Thiết lập kiểu chữ in đậm
		- Nhận **bold** hoặc là **normal** 
		- Đặt giá trị từ 100 - 900, 500 là bắt đầu viết đậm
### Dòng văn bản
- Đường cơ sở (baseline): là đường ngang mà các chữ cái đứng thẳng lên trên 
- Chiều cao dòng (line-height): khoảng cách giữa các đường cơ sở của các dòng trong một đoạn văn bản
![[Pasted image 20260316212509.png]]
- **line-height**: thiết lập chiều cao cho bộ chọn, có lấy các giá trị:
	- number: thiết lập chiều bao bằng number lần cỡ chữ hiện tại của trình duyệt
	- numem: thiết lập chiều cao bằng number lần chiều cao hiện thời
	- ...%: thiết lập bằng ...% của chiều cao của phần tử được kế thừa
- **text-align**: căn lề: jusify, left, right, center
- **text-decoration**: trang trí với đường kẻ, nhận giá trị:
	- none: không có
	- underline: dưới chân
	- overline: ở trên đầu
	- line-through: gạch đi
	- **KHÔNG CÓ TÍNH KẾ THỪA**
- **text-indent**: Thụt lề, nếu giá trị âm thì sẽ lùi ra ngoài, nếu giá trị dương thì lùi về phía trong
### Tính kế thừa và chọn thứ tự
- Tự áp dụng cho các phần tử con cháu trong mô hình cây HTML
- Ưu tiên định dạng viết **cuối cùng** 
- **!important**: ưu tiên cao nhất
- sao:  bộ chọn với ưu tiên thấp nhưng chọn tất cả các phần tử chưa có định dạng (Những cái có thì sẽ overwrite cái sao)
# Tạo màu cho chữ và nền 
- Hệ RGB: lấy theo R, G, B, mỗi giá trị chạy từ 0 - 255 (có 256 màu), mỗi nhóm giá trị x, x, x là 1 màu xám => có 256 màu xám khác nhau
- HSL: Hue (0 - 360 độ), Saturation (0 - 100%), Lightness (0 - 100%)
- color: màu cho màu nổi (chữ)
- background-color: màu nền
- CSS3 có sẵn 140 màu (lấy bằng tên)
- Dùng border định dạng màu khung nền cùng với những thuộc tính khác **KHÔNG CÓ TÍNH KẾ THỪA**
### Thiết lập bộ chọn cho phần tử có quan hệ
- E F: Con cháu. F là phần tử con, cháu của E (E ở trên F trong cây HTML)
-  E > F: Cha con. F là phần tử con của E (trực tiếp)
- E + F: Anh em liền kề. E có ngay sau F và E, F chung phần tử cha
- E ~ F: Anh em không cần liên tục, nhưng E, F có chung phần tử cha	![[Pasted image 20260316213219.png]]
- *VỚI ĐIỀU KIỆN!!! HOẶC LÀ ĐỨNG TRƯỚC/ ĐỨNG SAU*
![[Pasted image 20260316213526.png]]
# Định dạng khung
- Phân loại khối và nội tuyến:
	- Về nội dung thì sẽ là khối (tách riêng dòng ra)
	- Về định dạng hoặc là input thì sẽ là nội tuyến (giữ nguyên, không xuống dòng)
	- Dùng thuộc tính display: none, span (inline, block) để điều chỉnh có hiển thị, hiển thị inline hay là block
	![[Pasted image 20260316213723.png]]
- Định dạng khung:
	- Width, height: chỉ áp dụng cho phần tử khối
	- padding: vùng đệm, khoảng cách từ nội dung đến đường viền của khung (inside)
	- margin: khoảng cách từ khung đến đường viền nội dung xung quanh (outside)
	![[Pasted image 20260316213825.png]]
	- border:
		- color: màu viền
		- width: độ dày của đường viền
		- style: kiểu đường viên: **none, solid, dotted, dashed, double, inset, outset, ridge, groove**
		- border: Gán gái trị của color, width, style vào cùng 1 thuộc tính
- Bộ chọn đặc biệt:
	- .class (lớp) (CHẤM)
	![[Pasted image 20260316213928.png]]
	- #id name (định danh) - thăng
	![[Pasted image 20260316213951.png]]
	- chọn thuộc tính [ ] (chọn thuộc tính) (NGOẶC VUÔNG)
	![[Pasted image 20260316214012.png]]
	- Lưu ý:
		- Tên id, class case sensitive
		- ít nhất 1 kí tự, không phải số, không bắt đầu bằng số, không cách or special
		- Một phần tử có thể thuộc nhiều lớp khác nhau (class)
# Mức độ ưu tiên của bộ chọn
- :pseudo-class
![[Pasted image 20260316214058.png]]
- ::pseudo-element
![[Pasted image 20260316214111.png]]
- Mức độ:
	- !important
	- inline css
	- css related to device size
	- trọng số
	- nguyên tắc cuối
	- kế thừa từ cha
	- mặc định trình duyệt
- Giá trị trọng số của bộ chọn:
	- id = 100
	- class, pseudo-class, attribute selectors = 10
	- element, pseudo-element = 1
	- sao = 0

---
# Hướng nghiệp với tin học
## Dịch vụ sửa chữa và bảo trì máy tính
Những gì mình sẽ làm:
- Kiểm soát, duy trì hoạt động của máy
- Xác định, khắc phục lỗi
- Sửa, lắp, thay thế linh kiện
- Phát hiện nguyên nhân hỏng thiết bị
- Nâng cấp hoặc bổ sung thiết bị
- thay màn hình/ thay bo mạch chủ
Làm 2:
- Phần mềm driver
- Cài thông dụng: OS, cấu hình mạng
- Đảm bảo kết nối mạng
- Update phần mềm
- No virus
Làm 3:
- Tech support
Cần biết gì:
- Phần cứng: hiểu cơ bản, biết lắp và sửa
- Phần mềm: Biết sửa, cài phần mềm(hệ điều hành, văn phòng, trình duyệt, ...), virus killer
- Skill
	- Học hỏi
	- Cập nhật kiến thức
	- Giao tiếp
	- Quản lí thời gian
Nhu cầu:
- ngày càng tăng cao
- ngành: kĩ thuật sửa, lắp ráp máy, công nghệ kĩ thuật phần cứng, công nghệ kĩ thuật phần mềm, công nghệ thông tin
## Quản trị trong ngành công nghệ thông tin
Công việc gì:
- Quản trị mạng
- Bảo mật hệ thống thông tin
- Quản trị và bảo trì hệ thống
Kiến thức:
- Mạng máy tính
- Bảo mật máy tính
- Quản lí hệ thống
- Luật pháp và tuân thủ quy định
Skill:
- Giao tiếp
- Quản lí thời gian
- Cập nhật kiến thức mới
Các việc liên quan đang có nhu cầu:
- Quản trị mạng
- Bảo mật hệ thống thông tin
- Quản trị và bảo trì hệ thống
Những ngành có thể học:
- Quản trị mạng máy
- Quản trị hệ thống
- An ninh mạng
- Hệ thống thông tin
- Mạng máy tính và truyền thông dữ liệu
# Thiết bị mạng

# Đường truyền mạng và ứng dụng
# Làm quen với học máy
tags:
[[MOC ICT]]
