## Task01

> Thực hiện: Võ Xuân Khang

### Mục lục.

[1. Tổng quan C++](#tongquan)

[1.1 Hướng đối tượng](#huongdoituong)

[1.2 Thư viện chuẩn](#thuvien)

[1.3 Bảng ANSI](#ANSI)

[1.4 Học và sử dụng](#hoc&dung)

[2. Cú pháp cơ bản](#cuphap)

[2.1 Cấu trúc chương trình C++](#cautruc)

[2.2 Biên dịch và thực thi chương trình C++](#biendich&thucthi)

[2.3 Dấu chấm phẩy trong C++](#champhay)

[2.4 Định danh trong C++](#dinhdanh)

[2.5 Từ khóa](#keyword)

[2.6 Khoảng trắng trong C++](#whitespace)

### 1.Tổng quan C++

<a name='tongquan'></a>

- C++ là ngôn ngữ lập trình kiểu tĩnh, biên dịch, có chung mục đích, phân biệt chữ hoa chữ thường, ở dạng tự do mà hỗ trợ thủ tục lập trình hướng đối tượng và lập trình chung

- C++ được xem như một ngôn ngữ lập trình bậc trung vì nó bao gồm sự kết hợp các tính năng của cả ngôn ngữ lập trình bậc cao và bậc thấp

- C++ được phát triển bởi [Bjarne Stroustrup](https://vi.wikipedia.org/wiki/Bjarne_Stroustrup) bắt đầu từ năm 1979 tại Bell Labs, Murray Hill, New Jersey; như là một sự tăng cường cho ngôn ngữ lập trình C và ban đầu nó có tên là C với các Classes nhưng sau đó được đổi tên là C++ vào năm 1983

- C++ là bản cải tiến của C và hầu như là bất kì chương trình C nào cũng là chương trình C++ tương đương 

**NOTE**: Một ngôn ngữ lập trình được gọi là sử dụng kiểu tĩnh khi kiểu kiểm tra được thực hiện trong suốt thời gian biên dịch chứ không phải thời gian chạy

#### 1.1 Hướng đối tượng

<a name='huongdoituong'></a>

C++ hỗ trợ đầy đủ ngôn ngữ lập trình hướng đối tượng, bao gồm 4 cái chính:
- Đóng gói
- Ẩn dữ liệu
- Kế thừa
- Đa hình

#### 1.2 Thư viện chuẩn

<a name='thuvien'></a>

C++ chuẩn bao gồm 3 phần chính
- Ngôn ngữ cốt lõi: biến, kiểu dữ liệu...
- Thư viện chuẩn cung cấp các chức năng phong phú như: định dạng file, chuỗi, ....
- Thư viện mẫu chuẩn cung cấp các phương thức phong phú thao tác cấu trúc dữ liệu...

#### 1.3 Bảng ANSI

<a name='ANSI'></a>

- ANSI chuẩn cố gắng đảm bảo rằng C++ là hợp lệ - nghĩa là code bạn viết cho trình biên dịch của Microsoft sẽ chạy mà không có lỗi, sử dụng trình biên dịch trên MAC, Linux, Windows box, an Alpha...
- ANSI chuẩn đã ổn định, tất cả các nhà sản xuất trình biên dịch C++ đều hỗ trợ ANSI

#### 1.4 Học và sử dụng C++

<a name='hoc&dung'></a>

- Điều quan trọng nhất khi học C++ là tập trung vào các khái niệm và không bị lạc trong ngôn ngữ kĩ thuật chi tiết 
- C++ được sử dụng khá phổ biến 
- C++ được sử dụng nhiều để viết trình điều khiển thiết bị và các phần mềm khác bằng cách thao tác trực tiếp với phần cứng dưới sự kiểm soát thời gian thực
- C++ được sử dụng nhiều trong việc giảng dạy và học tập
- Bất kì ai dùng PC chạy Windows hay Apple Macintosh đều gián tiếp dùng C++ vì giao diện người dùng của các hệ thống này sử dụng C++

### 2. Cú pháp cơ bản

<a name='cuphap'></a>

Một chương trình C++ được định nghĩa như một tập hợp các đối tượng 
- Đối tượng (objects) có các thuộc tính và hành vi
- Lớp (class) được định nghĩa như một mẫu/kế hoạch chi tiết mô tả các hành vi trạng thái mà đối tượng hỗ trợ 
- Phương thức: về cơ bản phương thức cũng như hành vi. Một lớp có thể chứa nhiều phương thức. Nó là trong phương thức được viết logics, dữ liệu được thao tác và các hành động được thực hiện 
- Trường hợp biến: mỗi đối tượng có một tập các biến cá thể duy nhất. Trạng thái của mỗi đối tượng được tạo ra bởi các giá trị được gán cho các biến cụ thể

#### 2.1 Cấu trúc chương trình C++

<a name='cautruc'></a>

`#include <iostream>
using namespace std;

// main() is where program execution begins.

int main() {
   cout << "Hello World"; // prints Hello World
   return 0;
}`


- Header: ngôn ngữ C++ định nghĩa một số header, nơi chứa thông tin cần thiết hoặc hữu ích cho chương trình của bạn. Đối với chương trình in *Hello world* này thì header `iostream` là cần thiết
- Dòng `using namespace std` nói với trình biên dịch là sử dụng *std namespace*. Std namespaces là quan hệ gần đây thêm vào cho C++ 
- Dòng `// main() is where program execution begins` là nơi chương trình bắt đầu thực hiện. Là dòng đơn có sẵn trong C++. Bắt đầu với // và kết thúc ở cuối dòng
- Dòng `int main()` là chức năng chính nơi chương trình bắt đầu thực hiện
- Dòng `cout<<"This is my first C++ program"` hiển thị *this is my first C++ program* ra màn hình
- Dòng `return 0` kết thúc hàm `main()` và trả về giá trị hàm bằng 0 thuộc kiểu interger (int)

#### 2.2 Biên dịch và thực hiện chương trình C++

<a name='biendich&thucthi'></a>

Xem cách lưu tệp tin, biên dịch và chạy chương trình. Làm theo các bước dưới đây
- Mở trình soạn thảo và ghi code 
- Lưu file với tên *hello.cpp*
- Mở **command prompt** và đi đến thư mục đã lưu file
- Kiểu "g++ hello.cpp" và nhấn Enter để biên dịch code của bạn. Nếu không có lỗi xảy ra thì command prompt sẽ đến dòng lệnh tiếp theo và sẽ tạo tệp tin thực thi
- Bây giờ, tệp tin thực thi sẽ chạy chương trình của bạn
- Bạn sẽ nhìn thấy `Hello world` được in trên cửa sổ màn hình
**NOTE**: 
- chắc chắn là g++ đang nằm trong đường dẫn và bạn đang chạy nó trong thư mục chứa chương trình hello.cpp
- Bạn có thể biên dịch thành C/C++ bằng cách sử dụng makefile. Để biết thêm thông tin chi tiết, bạn có thể kiểm tra Makefile Tutorial

#### 2.3 Dấu chấm phẩy và khối trong C++

<a name='champhay'></a>

- Trong C++ dấu chấm phẩy dùng để kết thúc một câu lệnh.
Ví dụ: Dưới dây là 3 câu lệnh khác nhau
`x=y;
y=y+1;
add(x,y);`
- Một khối là một tập các câu lệnh được kết nối 1 cách logic bao quanh bởi các dấu đóng mở ngoặc 
Ví dụ: 
`{
	cout<<"Hello World";
	return 0;
}`
- `x=y;
	y=y+1;
	add(x,y);`
	tương đương với `x=y; y=y+1; add(x,y);`

#### 2.4 Định dang trong C++

<a name='dinhdanh'></a>

Một định danh C++ là một cái tên được sử dụng để xác định một biến, hàm, lớp, module hay bất kì item nào khác do người dùng định nghĩa. C++ không cho phép kí tự đặc biệt như @, $, % trong định danh; Chữ hoa và chữ thường là khác nhau trong C++

#### 2.5 Từ khóa

<a name='keyword'></a>

Dưới đây là danh sách các từ dành riêng trong C++, không được sử dụng là hằng, biến hay bất cứ thứ gì khác 	
`
|--asm-------|--else---|--------new------|----this--|
|--auto------|	enum---|-----operator----|--throw---|
|--bool------|explici--|-----private-----|--true----|
|break-------|export---|-----protected-ơ-|----try---|
|case--------|extern---|	public-------|--typedef-|
|catch-------|false----|	register-----|--typeid__|
|char--------|float	---|reinterpret_cast-|typename--|
|class	-----|for------|return-----------|-union----|
|const	-----|friend---|	short--------|-unsigned-|
|const_cast--|goto-----|	signed-------|-using----|
|continue----|	if-----|	sizeof-------|-virtual--|
|default-----|inline---|	static-------|-void-----|
|delete	-----|int------|static_cast------|-volatile-|
|do----------|long-----|	struct-------|-wchar_t--|
|double	-----|mutable--|	switch-------|	while---|
|dynamic_cast|namespace|	template-----|	--------| 
`
#### 2.6 Khoảng trắng 

<a name='whitespace'></a>

- Một dòng mà chỉ chứa khoảng trắng được gọi là dòng trống thì trình biên dịch sẽ bỏ qua nó
- Dùng để mô tả kí tự blank, tab, kí tự mới...