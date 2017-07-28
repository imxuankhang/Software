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

[4. C++ decision making statements]

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



