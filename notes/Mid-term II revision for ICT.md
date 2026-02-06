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
- CSS ngoài (external): Dùng một tệp .css mở rộng bên ngoài rồi link lại với thẻ link vào file HTML. Hoặc dùng @import
- CSS nội tuyến (inline): Dùng thẻ style lồng vào trong các thuộc tính ở file HTML
### Vai trò, ý nghĩa 
- Tách nhập nội dung và định dạng thành 2 việc độc lập
- Viết 1 lần, áp dụng, thay đổi nhiều lần
- Kết nối với bất kì trang web nào
# Định dạng văn bản bằng CSS
### Phông chữ
- Dùng **font-family** để chọn phông
	- Phân theo họ: serif (có chân), sans-serif (không có chân), monospace (dàn đều), cursive (viết tay), fantasy(trừu tượng)
	- Có thể nhận giá trị là một danh sách các tên font, trình duyệt sẽ lựa qua và tìm cái hiển thị văn bản
- Dùng **font-style** chọn kiểu chữ
	- Thiết lập in nghiêng hay in thường: nhận giá trị **normal** hay là **italics** 
- Dùng **font-size** chọn cỡ, nhận các giá trị:
	- Chinh xác: cm, mm, inch, px, pt
	- Tương đối:
		- em: so với cỡ chữ hiện thời của trình duyệt - phần tử ở phía trước
		- ex: so với chiều cao chữ x của cỡ hiện thời - 
		- rem: so với cỡ của phần tử HTML gốc (root)
		- %: theo phần trăm của phần tử cha
		- Mức: xx-small, x-small, small, medium, x-large, xx-large, mặc định là medium
- Dùng **font-weight** chọn độ in đậm
	- Thiết lập kiểu chữ in đậm
		- Nhận **bold** hoặc là **normal** 
		- Đặt giá trị từ 100 - 900, 500 là bắt đầu viết đậm
### Màu chữ
- Color: thiết lập mùa chữ
### Dòng văn bản
- Đường cơ sở (baseline): là đường ngang mà các chữ cái đứng thẳng lên trên 
- Chiều cao dòng (line-height): khoảng cách giữa các đường cơ sở của các dòng trong một đoạn văn bản
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
- Hệ RGB: lấy theo R, G, B, mỗi giá trị chạy từ 0 - 255 (có 256 màu)
- HSL: Hue (0 - 360 độ), Saturation (0 - 100%), Lightness (0 - 100%)
- color: màu cho màu nổi (chữ)
- background-color: màu nền
- Dùng border định dạng màu khung nền cùng với những thuộc tính khác **KHÔNG CÓ TÍNH KẾ THỪA**
### Thiết lập bộ chọn cho phần tử có quan hệ
- E F: Con cháu. F là phần tử con, cháu của E (E ở trên F trong cây HTML)
-  E > F: Cha con. F là phần tử con của E (trực tiếp)
- E + F: Anh em liền kề. E có ngay sau F và E, F chung phần tử cha
- E ~ F: Không cần liên tục, nhưng E, F có chung phần tử cha
# Định dạng khung
- Phân loại khối và nội tuyến:
	- Về nội dung thì sẽ là khối (tách riêng dòng ra)
	- Về định dạng hoặc là input thì sẽ là nội tuyến (giữ nguyên, không xuống dòng)
	- Dùng thuộc tính display: none, span (inline, block) để điều chỉnh có hiển thị, hiển thị inline hay là block
- Định dạng khung:
	- Width, height: chỉ áp dụng cho phần tử khối
	- padding: vùng đệm, khoảng cách từ nội dung đến đường viền của khung (inside)
	- margin: khoảng cách từ khung đến đường viền nội dung xung quanh (outside)
	- border:
		- color: màu viền
		- width: độ dày của đường viền
		- style: kiểu đường viên: **none, solid, dotted, dashed, double, inset, outset, ridge, groove**
		- border: Gán gái trị của color, width, style vào cùng 1 thuộc tính
- Bộ chọn đặc biệt:
	- .class (lớp)
	- #id name (định danh)
	- chọn thuộc tính [ ] (chọn thuộc tính)
	- Lưu ý:
		- Tên id, class case sensitive
		- ít nhất 1 kí tự không phải số, không bắt đầu bằng số, không cách or special
		- Một phần tử có thể thuộc nhiều lớp khác nhau (class)
# Mức độ ưu tiên của bộ chọn
- :pseudo-class
- ::pseudo-element
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
tags:
#ICT
[[MOC ICT]]
