# Task 04

> Thực hiện: Võ Xuân Khang

## Mục lục:

[1. Storage Classes in C++ (lớp lưu trữ)](#lopluutru)

[1.1 The auto Storage Class](#lopauto)

[1.2 The register Storage Class](#lopregister)

[1.3 The static Storage Class](#lopstatic)

[1.4 The extern Storage Class](#lopextern)

[1.5 The mutable Storage Class](#lopmutable)

[2. Operators in C++(toán tử)](#toantu)

[2.1 Arithmetic Operators](#toantuArithmetic)

[2.2 Relational Operators](#toantuRelational)

[2.3 Logical Operators](#toantuLogical)

[2.4 Bitwise Operators](#toantuBitwise)

[2.5 Assignment Operators](#toantuAssignment)

[2.6 Misc Operators](#toantuMisc)

[2.7 Operators Precedence](#toantuPrecedence)

[3. C++ loop types (vòng lặp)](#vonglap)

[3.1 Loop Control Statements](#caulenhdieukhien)

[3.2 The Infinite Loop](#lapvohan)

[4. C++ decision making statements](#tuyenboraquyetdinh)

[4.1 The ?: Operator]

## 1. Storage Classes in C++ (lớp lưu trữ)

<a name='lopluutru'></a>

Lớp lưu trữ xác định phạm vi (khả năng hiển thị) và thời gian tồn tại của các biến hoặc hàm trong một chương trình C++. Các lớp lưu trữ phổ biến được sử dụng trong một chương trình C++
- auto
- register
- static
- extern
- mutable

### 1.1  The auto Storage Class

<a name='lopauto'></a>

- Lớp lưu trữ **auto** là lớp lưu trữ mặc định cho tất cả các biến cục bộ

```
{
	int mount;
	auto int mounth;
}
```

- Ví dụ ở trên xác định 2 biến với cùng lớp lưu trữ, **auto** chỉ được sử dụng trong hàm tức là biến cục bộ

### 1.2 The register Storage Class

<a name='lopregister'></a>

- Lớp lưu trữ **storage** được sử dụng để xác định biến cục bộ mà biến đó được lưu trữ trong một thanh ghi thay vì RAM. Nghĩa là biến có kích thước tối đa bằng kích thước đăng kí và không có toán tử **&** được áp dụng cho nó

```
{
	register int miles;
}
```

**register** chỉ được sử dụng cho các biến đòi hòi truy cập nhanh như máy đếm. Lưu ý rằng việc xác định "register" không có nghĩa là biến sẽ được lưu trữ trong thanh ghi. Nó có nghĩa là nó có thể được lưu trữ trong thanh ghi tùy thuộc vào phần cứng và các hạn chế thực hiện

### 1.3 The static Storage Class

<a name='lopstatic'></a>

- Lớp lữu trữ **static** hướng dẫn trình biên dịch giữ một biến cục bộ tồn tại trong suốt thời gian thực hiện chương trình thay vì khởi tạo và hủy nó mỗi khi cần dùng tới. Do đó làm cho biến cục bộ tĩnh cho phép chúng duy trì giá trị của nó giữa các lần gọi hàm
- Các bổ nghĩa tĩnh cũng có thể áp dụng cho biến toàn cục. Khi được thực hiện, nó là nguyên nhân làm cho phạm vi của biến đó bị giới hạn trong tệp tin mà nó được khai báo
- Trong C++, khi lớp lưu trữ static được sử dụng trên một trong những lớp dữ liệu, nó chỉ tạo ra một bản sao của lớp dữ liệu đó và được chia sẻ bởi tất cả các đối tượng trong lớp của nó 

```
#include <iostream>
 
// Function declaration
void func(void);
 
static int count = 10; /* Global variable */
 
main() {
   while(count--) {
      func();
   }
   return 0;
}

// Function definition
void func( void ) {
   static int i = 5; // local static variable
   i++;
   std::cout << "i is " << i ;
   std::cout << " and count is " << count << std::endl;
}
```
Kết quả
```
i is 6 and count is 9
i is 7 and count is 8
i is 8 and count is 7
i is 9 and count is 6
i is 10 and count is 5
i is 11 and count is 4
i is 12 and count is 3
i is 13 and count is 2
i is 14 and count is 1
i is 15 and count is 0
```

### 1.4 The extern Storage Class 

<a name='lopextern'></a>

- **extern** được sử udngj để tuyên bố một biến toàn cục hoặc hàm trong các tệp tin khác nhau 
- Các sử đổi **extern** thường được sử dụng khi có hai hoặc nhiều tệp tin chia sẻ cùng một biến toàn cục hoặc hàm như dưới đây

**Tệp tin đầu tiên: main.cpp**
```
#include <iostream>
 
int count ;
extern void write_extern();
 
main() {
   count = 5;
   write_extern();
}
```
**Tệp tin thứ hai: support.cpp**
```
#include <iostream>
 
extern int count;
 
void write_extern(void) {
   std::cout << "Count is " << count << std::endl;
}
```
Ở đây, từ khóa **extern** đang được sử dụng để tuyên bố `count` trong tệp tin khác. Kết quả của 2 tệp tin trên là:
`$g++ main.cpp support.cpp -o write`

Điều này tạo ra chương trình thực thi **write**,thử  thực thi lại **write** và kiểm tra kết quả sau:
```
$./write
5
```

### 1.5 The mutable Storage Class

<a name='lopmutable'></a>

- **mutable** chỉ áp dụng cho đối tượng lớp. Nó cho phép một thành viên của một đối tượng ghi đè lên *constness*

## 2. Operators in C++ (toán tử)

<a name='toantu'></a>

Toán tử là một kí hiệu cho phép trình biên dịch thực hiện các thao tác toán học hoặc logic. C++ có nhiều toán tử được xây dựng sẵn và cung cấp các kiểu toán tử sau đây:
- Arithmetic Operators
- Relational Operators 
- Logical Operators
- Bitwise Operators
- Misc Operators
Chương này sẽ kiểm tra từng toán tử số học, quan hệ, logic, toán tử trên bit, gán

### 2.1 Arithmetic Operators

<a name='toantuArithmetic'></a>

Dưới đây là các toán tử số học được hỗ trợ bởi C++. Gỉa sử biến A được gán giá trị là 10 và biến B là 20

<img src = "https://github.com/imxuankhang/Software/blob/master/Cpp/Task04/Images/img1.PNG">

### 2.2 Relational Operators

<a name='toantuRelational'></a>

Dưới đây là các toán tử quan hệ được hỗ trợ bởi C++. Gỉa sử biến A được gán giá trị là 10 và biến B là 20

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task04/Images/img2.PNG">

### 2.3 Logical Operators 

<a name='toantuLogical'></a>

Dưới đây là các toán tử quan hệ được hỗ trợ bởi C++. Gỉa sử biến A được gán giá trị là 1 và biến B là 0

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task04/Images/img3.PNG">

### 2.4 Bitwise Operators

<a name='toantuBitwise'></a>

Toán tử bitwise làm việc trên các bit và thực hiện các thao tác với bit. Các bảng giá trị của các phép toán trên bit như sau:

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task04/Images/img4.PNG">

Nếu A=60 và B=13, dưới đây là định dạnh của A và B ở dạng nhị phân
A = 00111100
B = 00001101
---------------
A&B = 00001100 (phép AND)
A|B = 00111101 (phép OR)
A^B = 00110001 (phép XOR)
~A = 11000011  (phép NOT)

Các toán tử Bitwise được hỗ trợ bởi C++ được liệt kê dưới. Gỉa sử biến A=60 và B=13

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task04/Images/img5.PNG">

### 2.5 Assignment Operators

<a name='toantuAssignment'></a>

Dưới đây là các toán tử gán được hỗ trợ bởi C++

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task04/Images/img6.PNG">

### 2.6 Misc Operators

<a name='toantuMisc'></a>

Đây là một vài toán tử khác được hỗ trợ bởi C++ 

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task04/Images/img7.PNG">

### 2.6 Operators Precedence in C++ (toán tử ưu tiên)

<a name='toantuPrecedence'></a>

- Thứ tự thực hiện các toán tử được xác định bởi nhóm các thuật ngữ trong một biểu thức. Một vài toán tử có độ ưu tiên cao hơn các toán tử khác. Ví dụ, toán tử nhân có độ ưu tiên cao hơn toán tử bổ sung
- Ví dụ **x=7+3*2**, ở đây x có giá trị là 13, không phải 20 vì toán tử * được thực hiện trước toán tử +
- Dưới đây là các toán tử đã được sắp xếp theo mức độ ưu tiên từ cao đến thấp

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task04/Images/img8.PNG">

## 3. C++ loop types (vòng lặp)

<a name='vonglap'></a>

- Trong những tình huống, bạn cần thực hiện lại một khối mã vài lần. Khi đó tuyên bố vòng lặp sẽ cho phép thực hiện một nhóm các câu lệnh nhiều lần và dưới đây vòng lặp đưới khái niệm một cách tổng quát trong hầu hết các ngôn ngữ lập trình 

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task04/Images/img9.PNG">

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task04/Images/img10.PNG">

### 3.1 Loop Control Statements

<a name='caulenhdieukhien'></a>

- Lệnh điều khiển vòng lặp thay đổi các thực hiện vòng lặp từ trình tự bình thường của nó
- C++ hỗ trợ các câu lệnh điều khiển vòng lặp sau

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task04/Images/img11.PNG">

### 3.2 Vòng lặp vô hạn

<a name='lapvohan'></a>

- Vòng lặp trở thành vòng lặp vô hạn nếu một điều kiện không bao giờ trở thành sai. Vòng lặp **for** thường được sử dụng cho mục đích này. Vì bạn có thể tạo một vòng lặp vô hạn bằng cách để biểu thức điều kiện trống
```
#include <iostream>
using namespace std;
 
int main () {

   for( ; ; ) {
      printf("This loop will run forever.\n");
   }

   return 0;
}
```
**Lưu ý:** Bạn có thể thoát khỏi vòng lặp vô hạn bằng cách ấn tổ hợp phím Ctrl + C

## 4. C++ decision making statements (câu lệnh điều kiện)

<a name='caulenhdieukien'></a>

- Các cấu trúc điều kiện  yêu cầu người lập trình chỉ định một hoặc nhiều điều kiện cần đánh giá hoặc kiểm tra bởi chương trình cùng với một câu lệnh. Câu lệnh sẽ được thực hiện nếu điều kiện được xác định là đúng, và tùy ý, các câu lệnh khác sẽ được thực hiện khi điều kiện được xác định là sai
- Dưới đây là hình thức chung của một cấu trúc ra quyết định điển hình trong hầu hết các ngôn ngữ lập trình

<img src = "https://github.com/imxuankhang/Software/blob/master/Cpp/Task04/Images/img12.PNG">

- C++ cung cấp dạng các câu lệnh điều kiện như sau

<img src ="https://github.com/imxuankhang/Software/blob/master/Cpp/Task04/Images/img13.PNG">

### 4.1 The ?: Operators

- Có thể sử dụng toán tử ? thay thế cho câu lênh **if...else**. Nó có dạng tổng quát như sau
`Exp1 ? Exp2 : Exp3;`
- Trường hợp exp1,exp2,exp3 là biểu thức thì lưu ý việc sử dụng và vị trí dấu hai chấm
- Gía trị của một biểu thức **?** được xác định như sau: exp1 được đánh giá, nếu nó là đúng thì exp2 được đánh giá và trở thành giá trị của biểu thức **?** biểu hiện. Nếu exp1 là sai thì exp3 được đánh giá và nó trở thành giá trị của biểu thức **?**




