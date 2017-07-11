# Task02

> Thực hiện: Xuân Khang

## Mục lục:

[1. Comments in C++](#comment)

[2. C++ data type](#datatype)

[2.1 Kiểu dữ liệu chính](#kieunguyenthuy)

[2.2 Typedef](#typedef)

[2.3 Kê khai](#kekhai)

## 1. Comments in C++ 

<a name='comment'></a>

- Là câu giải thích cho dòng lệnh mà bạn có thể đưa vào để người đọc hiểu rõ hơn về dòng code của mình. Tất cả các ngôn ngữ lập trình cho phép một số hình thức bình luận 
- C++ hỗ trợ bình luận đơn dòng và đa dòng. Tất cả các kí tự bên trong dòng bình luận đều được trình biên dịch bỏ qua. 
- Dòng bình luận bắt đầu bằng /* và kết thúc */
Ví dụ

```
/* this is a comment */
```
- Dòng bình luận cũng có thể bắt đầu bằng // và kéo dài đến cuối dòng
Ví dụ

```
// this is a comment 
```

## 2. C++ data types

<a name='datatype'></a>

- Khi lập trình với bất kì ngôn ngữ lập trình nào, bạn cần sử dụng các biến khác nhau để lưu trữ những thông tin khác nhau. Các biết là không có gì nhưng có vị trí bộ nhớ dự trữ để lưu trữ cá giá trị. Có nghĩa là khi bạn tạo một biến là đồng thời bạn cũng dự trữ một vài không gian bộ nhớ
- Bạn có thể lưu trữ thông tin của nhiều dạng dữ liệu khác nhau như chuỗi, chuỗi rộng, số nguyên,....Dựa vào kiểu dữ liệu của một biến, hệ điều hành cấp phát bộ nhớ và phân chia những gì có thể lưu trữ trong bộ nhớ đó
### 2.1 Các kiểu dữ liệu chính

<a name='kieunguyenthuy'></a>

Có 7 kiểu cơ bản trong C++

|-------type----------|-------keyword------|

|-----bolean----------|------bool----------|

|---character---------|-------char---------|

|----integer----------|----------int-------|

|floating point-------|-----float----------|

|double floating point|-----double---------|

|--valueles-----------|--------void--------|

|wide character-------|-----wchar t--------|

- Một số loại nâng cao:
	- wcharsigned
	- unsigned
	- short
	- long

- Bảng số lượng giá trị bộ nhớ, giá trị tối đa, giá trị tối thiểu của các loại biến 

|-----type-----------|chiều rộng bit-------|độ dài--------------------|

|---char-------------|1 byte---------------| -128 đến 127 hoặc 0->255-|

|unsigned char-------|1 byte---------------| 0 -> 255 ----------------|

|---signed char------|----1 byte-----------| -128 -> 127 -------------|

|int ----------------|4 byte --------------|- 2 mũ 31 đến 2 mũ 31 ----|

|unsigned int -------|4 byte---------------| 0 đến 2 mũ 32------------|

|signed int----------|4 byte---------------|tương tự int -------------|

|short int-----------|2 byte---------------|-32768 to 32767 ----------|

|unsigned short int--|2 byte---------------|0 to 65535----------------|

|signed short int----|2 byte---------------|tương tự short int--------|

|long int------------|8 byte---------------|-3 mũ 32 đến 3 mũ 32------|

|signed long int-----|8 byte---------------| tương tự long int -------|

|unsigned long int---|8 byte --------------| 0  đến 2 mũ 64-----------|

|float --------------|4 byte---------------| 7 digits-----------------|

|double--------------|8 byte---------------| 15 digits----------------|

|long double --------|8 byte---------------|15 digits-----------------|

|wchar t-------------|2 or 4 byte----------| 1 wide character---------|

- Kích thước của biến có thể khác với các giá trị được ghi trên bảng tùy vào trình biên dịch và máy tính bạn đang sử dụng 
- Để chắc chắn ta sử dụng hàm sau:

```
#include <iostream>

using namespace std;

int main()
{
	cout << "Size of char : " << sizeof(char) << endl;
	cout << "Size of int : " << sizeof(int) << endl;
	cout << "Size of short int : " << sizeof(short int) << endl;
	cout << "Size of long int : " << sizeof(long int) << endl;
	cout << "Size of float : " << sizeof(float) << endl;
	cout << "Size of double : " << sizeof(double) << endl;
	cout << "Size of wchar_t : " << sizeof(wchar_t) << endl;
	return 0;
}
```
- Sử dụng **endl** để xuống dòng và **sizeof** để có được kích thước của từng loại dữ liệu khác nhau

### 2.2  **typedef**

<a name='typedef'></a>

Bạn có thể đặt một cái tên mới cho dạng dữ liệu hiện có bằng cách sử dụng *typedef* với cú pháp:

`typedef type newname`

### 2.3 Các dạng kê khai

<a name='kekhai'></a>

Để tạo một điều tra ta sử dụng từ khóa **enum** 

` enum enum-name { list of names } var list;`

Ví dụ, liệt kê các màu và biến *c* của kiểu màu. Cuối cùng, *c* được gán là *blue*

``` 
enum color { blue, red, black} c;

c = blue;
``` 
Theo mặc định, giá trị đầu tiên của tên đầu tiên là 0, tiếp theo là 1,... nhưng ta có thể cho một tên một giá trị cụ thể như ví dụ dưới

`enum color { red, green=5, blue };`

Tại đây tên *blue* sẽ có giá trị là 6
