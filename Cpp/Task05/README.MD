# Task05

> Thực hiện: Võ Xuân Khang

## Mục lục:

[1. C++ Functions (Hàm)](#ham)

[1.1 Defining a Function](#defining)

[1.2 Function Declarations](#declaration)

[1.3 Calling a Function](#calling)

[1.4 Default Values for Parameters](#default_values)

[2. Numbers in C++](#number)

[2.1 Defining Numbers in C++](#defining)

[2.2 Math Operators in C++](#toan_tu)

[2.3 Random Numbers in C++](#random_numbers)

[3. C++ arrays](#mang)

[3.1 Declaring Arrays](#declaring)

[3.2 Initializing Arrays](#initializing)

[3.3 Accessing Array Elements](#accessing)

[3.4 C++ Arrays in Detail](#detail)

[4. C++ Strings (chuỗi)](#chuoi)

[4.1 The C-Style Character Strings](#charaters_string)

[4.2 The String Class in C++](#string_class)

## 1. C++ Functions(Hàm)

<a name='ham'></a>

- Một hàm là một nhóm các câu lệnh cùng thực hiện một nhiệm vụ. Mỗi chương trình có ít nhất một hàm, đó là hàm **main()** 
- Ta có thể phân chia code của mình thành các hàm riêng biệt tùy thuộc vào sở thích, phong cách code của mình. Thông thường ta chia đoạn code thành nhiều hàm nhằm giúp đơn giải việc giải toán
- Một lời khai báo hàm nói với trình biên dịch về tên hàm, kiểu trả về, tham số. Một định nghĩa hàm cung cấp cấu trúc của hàm
- Thư viện chuẩn của C++ cung cấp nhiều hàm tích hợp sẵn mà ta có thể sử dụng khi viết chương trình. Ví dụ như hàm **Strcat()** để nối 2 chuỗi, hàm **memcpy()** để sao chép một vị trí bộ nhớ đến vị trí khác ....
- Các ngôn ngữ lập trình khác nhau có các hàm khác nhau

### 1.1 Defining a Function

<a name='defining'></a>

- Có dạng

```
return_type function_name( parameter list ) {
   body of the function
}
```
- Một định nghĩa hàm bao gồm tiêu đề hàm và thân hàm
	- Return type: là kiểu giá trị mà hàm trả về. Nếu muốn hàm hoạt động theo mong muốn mà không trả về giá trị thì kiểu trả về trong trường hợp này là **void()**
	- Function name: đây là tên của thực của hàm, tên và danh sách tham số cùng nhau làm định danh cho hàm
	- Parameters: giống như một trình giữ chố, khi hàm được gọi ta truyền một giá trị cho tham số đó. Gía trị này được gọi là tham số thực. Tham số là tùy chọn, nghĩa là một hàm có thể không có tham số
	- Function Body: chứa một tập hợp các câu lệnh định nghĩa hàm đó 

Ví dụ: dưới đây là hàm **max()**, hàm này giữ 2 tham số là *num1,num2* và trả về số lớn nhất trong 2 số 
```
// function returning the max between two numbers
 
int max(int num1, int num2)  {
   // local variable declaration
   int result;
 
   if (num1 > num2)
      result = num1;
   else
      result = num2;
 
   return result; 
}
```

### 1.2 Function Declarations

<a name='declaration'></a>
 
 - Một lời khai báo hàm nói với trình biên dịch tên hàm và cách gọi hàm. Phần thân của hàm có thể được xác định riêng 
 - Một khai báo hàm có các phần
 
 `return_type function_name( parameter list );`

 Đối với hàm **max()** được xác định ở trên, dưới đây là khai báo hàm:

 `int max(int num1, int num2);`

 - Tên tham số không quan trọng trong khai báo hàm, khai báo hàm chỉ yêu cần loại của chúng. Dưới đây là một khai báo hợp lệ:

 `int max(int, int);`

 - Khai báo hàm yêu cầu khi bạn xác định một hàm bên trong một tệp tin nguồn và bạn gọi hàm trong một tệp tin khác thì bạn phải kahi báo hàm ở đầu của tệp tin gọi hàm.

### 1.3 Calling a Function

<a name='calling'></a>



