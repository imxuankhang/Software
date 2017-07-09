# Task03

> Thực hiện: Võ Xuân Khang

## Mục lục:

[1. Dạng biến trong C++](#bien)

[1.1 Định nghĩa, khai báo](#dinhnghia)

[1.2 Khai báo](#khaibao)

[1.3 Lvalues và Rvalues](#R&Lvalues)

[2. Phạm vi biến](#phamvi)

[2.1 Biến nội bộ](#local)

[2.2 Biến toàn cục](#global)

[3. Hằng](#hang)

[4. Bổ nghĩa](#bonghia)

## 1. Biến trong C 

<a name='bien'></a>

- Một biến cung cấp cho ta một tên bộ nhớ mà chương trình có thể thao tác được. Mỗi biến trong C++ có một dạng riêng, xác định kích thước và không gian bộ nhớ của biến cũng như phạm vi giá trí có thể lưu trữ trong bộ nhớ đó; và thiết lập hoạt động có thể áp dụng cho biến đó.
- Tên của biến có thể gồm chữ, số, và dấu gạch dưới `_`. Nó chỉ được bắt đầu với từ hoặc kí tự gạch dưới. Chữ hoa và chữ thường là khác nhau vì C++ phân biệt chữ hoa và chữ thường
**Dưới đây là một số dạng biến đơn giản**
<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task03/Images/img1.PNG">
- C++ cũng cho phép chấp nhận nhiều kiểu biến khác nhau, ta sẽ đề cập chúng ở các chương sau

### 1.1 Định nghĩa 

<a name='dinhnghia'></a>

Định nghĩa biến nghĩa là nói với trình biên dịch nơi và bao nhiêu để tạo bộ nhớ cho biến. Một định nghĩa biến xác định dạng dữ liệu, và chứa danh sách một hoặc nhiều biến cùng loại như sau

`type variable_list;`

*type* là một loại dữ liệu hợp lệ như *char,float,int,bool..* hoặc bất kì đối tương người dùng định nghĩa khác và *variable_list* gồm một nhiều tên định danh cách nhau bởi dấu *,*

`
int i,j,k;
char c, ch;
float f, salary;
`

Các biến có thể được khởi tạo (gán giá trị đầu) ngay lúc khai báo chúng

`int d=3,f=5`

Đối với khai báo không khởi tạo, giá trị ban đầu của tất cả các biến khác là không xác định 

### 1.2 Khai báo biến

<a name='khaibao'></a>

- Một khai báo biến rất hữu ích khi bạn sử dụng nhiều tệp tin và bạn cần xác định biến của bạn trong một trong những tệp tin hợp lệ tại thời điểm liên kết của chương trình. Bạn sẽ sử dụng từ khóa *extern* để khai báo một biến ở bất kì đâu. Mặc dù bạn có thể khai báo một biến nhiều lần trong một một chương trình C++, tuy nhiên nó chỉ được xác định một lần trong một file,hàm hay một khối mã 
**Ví dụ** biến được khai báo ở trên nhưng nó được xác định trong hàm *main()*

`
#include <iostream>

using namespace std;

// Variable declaration:

extern int a, b;

extern int c;

extern float f;

int main () 

{

	// Variable definition:

	int a, b;

	int c;

	float f;

 	// actual initialization

	a = 10;

	b = 20;

	c = a + b;

 	cout << c << endl ;

	f = 70.0/3.0;

	cout << f << endl ;

 	return 0;

}
`

- Tương tự như vậy, áp dụng cho khai báo hàm. Bạn có thể khai báo hàm ở trên, và nó được định nghĩa ở bất cứ nơi nào

`
// function declaration

int func();

int main() 

{

   // function call

   int i = func();

}

// function definition

int func() {

   return 0;

}
`


