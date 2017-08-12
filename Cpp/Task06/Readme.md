# Task06

> Thực hiện: Võ Xuân Khang

## Mục lục:

[1. C++ Pointers(con trỏ)](#contro)

[1.1 Con trỏ là gì?](#gioithieu)

[1.2 Cách sử dụng](#sudung)

[1.3 Chi tiết về con trỏ](#chitiet)

[2. C++ references(tham chiếu)](#thamchieu)

[2.1 Tham chiếu và con trỏ trong C++](#thamchieu&contro)

[2.2 Tạo tham chiếu trong C++](#tao)

[3. C++ Date and Time](#date&time)

[3.1 Date and Time hiện tại](#current)

[3.2 Định dạng Time sử dụng cấu trúc tm struct trong C++](#dinhdang)

[4. C++ Basic Input/Output](#input&output)

[4.1 Header file cho I/O](#headerfile)

[4.2 Standard Output Stream trong C++(cout)](#cout)

[4.3 Standard Input Stream trong C++(cin)](#cin)

[4.4 Standard Error Stream trong C++(cerr)](#cerr)

[4.5 Standard Log Stream trong C++(clog)](#clog)

## 1. C++ Pointers(con trỏ)

<a name='contro'></a>

- Con trỏ giúp việc thực hiện giải toán dễ dàng hơn, và làm cho một vài tác vụ trở nên linh hoạt hơn, như trong việc cấp phát bộ nhớ không thể thực hiện được mà không sử dụng con trỏ
- Ta biết, mỗi biến nằm trong một vùng nhớ nhất định và mỗi vùng nhớ có địa chỉ xác định có thể truy cập bằng cách sử dụng toán tử & điều đó sẽ biểu thị địa chỉ trong bộ nhớ. Xét ví dụ dưới đây sẽ in địa chỉ của các biến được xác định

```
#include <iostream>

using namespace std;

int main () {
   int  var1;
   char var2[10];

   cout << "Address of var1 variable: ";
   cout << &var1 << endl;

   cout << "Address of var2 variable: ";
   cout << &var2 << endl;

   return 0;
}
```
Khi đoạn code dưới đây được biên dịch và chạy sẽ cho kết quả:
```
Address of var1 variable: 0xbfebd5c0
Address of var2 variable: 0xbfebd5b6
```
### 1.1 Con trỏ là gì?

<a name='gioithieu'></a>

- Con trỏ là một biến chứ địa chỉ của một biến khác. Giống như biến hay hằng, bạn phải khai báo con trỏ trước khi bạn làm việc với nó. Hình thức chung để khai báo một con trỏ là:

`type *var-name;`

- Ở đây, *type* là kiểu dữ liệu của con trỏ và *var-name* là tên của biến con trỏ. Trong câu lệnh này, dấu hoa thị được sử dụng để chỉ một biến như một con trỏ. Dưới đây là khai báo con trỏ hợp lệ

```
int    *ip;    // pointer to an integer
double *dp;    // pointer to a double
float  *fp;    // pointer to a float
char   *ch     // pointer to character
```
- Sự khác biệt duy nhất giữa con trỏ của các kiểu dữ liệu khác nhau là kiểu dữ liệu mà biến hay hằng mà con trỏ trỏ tới 

### 1.2 Các sử dụng con trỏ

<a name='sudung'></a>

- Có một vài phép toán quan trọng giúp ta làm việc với con trỏ thường xuyên như:
	- định nghĩa biến con trỏ
	- gán địa chỉ của biến đến con trỏ
	- truy cập các giá trị biến địa chỉ trong biến con trỏ
Điều này được thực hiện bằng cách sử dụng toán tử * trả về giá trị của biến chứa trong địa chỉ được xác định bởi toán tử này. Ví dụ dưới dây là cách sử dụng những phép toán trên

```
#include <iostream>

using namespace std;

int main () {
   int  var = 20;   // actual variable declaration.
   int  *ip;        // pointer variable 

   ip = &var;       // store address of var in pointer variable

   cout << "Value of var variable: ";
   cout << var << endl;

   // print the address stored in ip pointer variable
   cout << "Address stored in ip variable: ";
   cout << ip << endl;

   // access the value at the address available in pointer
   cout << "Value of *ip variable: ";
   cout << *ip << endl;

   return 0;
}
```
Khi đoạn code trên được biên dịch và chạy, nó sẽ sản sinh ra kết qua sau:
```
Value of var variable: 20
Address stored in ip variable: 0xbfc601ac
Value of *ip variable: 20
```

### 1.3 Chi tiết về con trỏ 

<a name='chitiet'></a>

- Con trỏ có nhiều khái niệm nhưng dễ. Chúng rất quan trọng trong chương trình C++. Dưới đây là vài khái niệm quan trọng về con trỏ

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task06/Images/IMG1.PNG">

## 2. C++ References(tham chiếu)

<a name='thamchieu'></a>
 
 - Một biến tham chiếu là một **alias**, đó là cái tên khác cho biến đã tồn tại. Khi một tham chiếu được khởi tạo với một biến thì hoặc tên biến hoặc tên tham chiếu có thể được sử dụng để tham chiếu tới biến đó

