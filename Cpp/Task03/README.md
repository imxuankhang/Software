# Task03

> Thực hiện: Võ Xuân Khang

## Mục lục:

[1. Dạng biến trong C++](#bien)

[1.1 Variable definition](#dinhnghia)

[1.2 Variable declaration](#khaibao)

[1.3 Lvalues và Rvalues](#R&Lvalues)

[2. Variable Scope](#phamvi)

[2.1 Biến nội bộ](#local)

[2.2 Biến toàn cục](#global)

[2.3 Initializing local và global variables](#initializinglocal&globalvariables)

[3. Constants/Literals](#hang)

[3.1 Integer literals](#kitunguyen)

[3.2 Floating-point literals](#dauchamdong)

[3.3 Boolean literals](#kitubool)

[3.4 Character literals](#kitu)

[3.5 String literals](#kituchuoi)

[3.6 Defining Constants]

[3.7 The #define preprocessor]

[3.8 The const Keyword]

[4. Modifier Types](#bonghia)

## 1. Biến trong C 

<a name='bien'></a>

- Một biến cung cấp cho ta một tên bộ nhớ mà chương trình có thể thao tác được. Mỗi biến trong C++ có một dạng riêng, xác định kích thước và không gian bộ nhớ của biến cũng như phạm vi giá trí có thể lưu trữ trong bộ nhớ đó; và thiết lập hoạt động có thể áp dụng cho biến đó.
- Tên của biến có thể gồm chữ, số, và dấu gạch dưới `_`. Nó chỉ được bắt đầu với từ hoặc kí tự gạch dưới. Chữ hoa và chữ thường là khác nhau vì C++ phân biệt chữ hoa và chữ thường

**Dưới đây là một số dạng biến đơn giản**
<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task03/Images/img1.PNG">

- C++ cũng cho phép chấp nhận nhiều kiểu biến khác nhau, ta sẽ đề cập chúng ở các chương sau

### 1.1 Variable definition 

<a name='dinhnghia'></a>

- Định nghĩa biến nghĩa là nói với trình biên dịch nơi và bao nhiêu để tạo bộ nhớ cho biến. Một định nghĩa biến xác định dạng dữ liệu, và chứa danh sách một hoặc nhiều biến cùng loại như sau

`type variable_list;`

> *type* là một loại dữ liệu hợp lệ như *char,float,int,bool..* hoặc bất kì đối tương người dùng định nghĩa khác và *variable_list* gồm một nhiều tên định danh cách nhau bởi dấu *,*

```
int i,j,k;
char c, ch;
float f, salary;
```

- Các biến có thể được khởi tạo (gán giá trị đầu) ngay lúc khai báo chúng

`int d=3,f=5`

- Đối với khai báo không khởi tạo, giá trị ban đầu của tất cả các biến khác là không xác định 

### 1.2 Variable Declaration

<a name='khaibao'></a>

- Một khai báo biến rất hữu ích khi bạn sử dụng nhiều tệp tin và bạn cần xác định biến của bạn trong một trong những tệp tin hợp lệ tại thời điểm liên kết của chương trình. Bạn sẽ sử dụng từ khóa *extern* để khai báo một biến ở bất kì đâu. Mặc dù bạn có thể khai báo một biến nhiều lần trong một một chương trình C++, tuy nhiên nó chỉ được xác định một lần trong một file,hàm hay một khối mã 
**Ví dụ** biến được khai báo ở trên nhưng nó được xác định trong hàm *main()*

```
#include <iostream>
using namespace std;

// Variable declaration

extern int a, b;
extern int c;
extern float f;
int main ()
{
	
	// Variable definition
	
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
```


- Tương tự như vậy, áp dụng cho khai báo hàm. Bạn có thể khai báo hàm ở trên, và nó được định nghĩa ở bất cứ nơi nào

```
// function declaration

int func();
int main() 
{

// function call

int i = func();
}

// function definition

int func() 
{
	return 0;
}
```

### 1.3 Rvalues và Lvalues

<a name='R&Lvalues'></a>

- Có 2 loại biểu thức trong C++
	- Lvalue là biểu thức tham chiếu đến vị trí bộ nhớ. Một Lvalue có thể xuất hiện bên trái hoặc phải của một assignment
	- Rvalue là biểu thức tham chiếu đến giá trị được lưu tại một số địa chỉ trong bộ nhớ. Một Rvalue là một biểu thức mà không thể có giá trị được gán cho nó, nghĩa là một Rvalue có thể xuất hiện bên phải nhưng không xuất hiện bên trái của một assignment 
- Biến là Lvalue do đó có thể xuất hiện bên trái của một assignment. Các kí tự số là Rvalue và do đó không được gán hay xuất hiện bên trái của assignment
Ví dụ: đây là một code hợp lệ

`int g = 20;`

Dưới đây là không hợp lệ và có thể tạo ra lỗi biên dịch

`10 = 20`

## 2. Variable Scope

<a name='phamvi'></a>

- Phạm vi là khu vực của chương trình và nói một cách tổng quát là có 3 không gian, nơi mà biến được khai báo
	- Bên trong hàm hoặc khối mà biến nơi đó được gọi là biến nội bộ 
	- Trong định nghĩa tham số của hàm nơi biến được gọi là tham số chính thức 
	- Bên ngoài hàm nơi biến được gọi là biến toàn cục 

### 2.1 Biến cục bộ

<a name='local'></a>

Biến cục bộ được khai báo bên trong một hàm. Bạn chỉ được sử dụng chúng trong hàm đó 

```
#include <iostream>
using namespace std;
 int main () 
 {
 
   // Local variable declaration:
 
   int a, b;
   int c;
 
   // actual initialization
 
   a = 10;
   b = 20;
   c = a + b;
   cout << c;
   return 0;
}
```

### 2.2 Biến toàn cục

- Biến toàn cục được xác định bên ngoài của tất cả các hàm, thường là trên đầu của chương trình. Gía trị của các biến toàn cục được giữ trong suốt chương trình. 
- Chúng có thể được sử dụng bởi bất kì hàm nào

```
#include <iostream>
using namespace std;
 
// Global variable declaration:

int g;
 int main () 
{

   // Local variable declaration:

   int a, b;
 
   // actual initialization

   a = 10;
   b = 20;
   g = a + b; 
   cout << g;
   return 0;
}
```
- Một chương trình có thể có biến cục bộ và biến toàn cục cùng tên với nhau. Nhưng giá trị của biến cục bộ mới được hàm chấp nhận 

```
#include <iostream>
using namespace std;
 
// Global variable declaration:

int g = 20;
int main () {

   // Local variable declaration:

   int g = 10; 
   cout << g;
   return 0;
}
```
### 2.3 Initializing local và global variables

<a name='initializationlocal&globalvariables'></a>

- Khi biến cục bộ được xác định, nó không được khởi tạo bởi hệ thống mà chính bạn phải khởi tạo nó. Biến toàn cục được khởi tạo tự động bởi hệ thống khi bạn xác định, định nghĩa nó 
<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task03/Images/img2.PNG">

## 3. Constants/Literals

<a name='hang'></a>

- Hằng là giá trị mà chương trình không thể thay đổi và nó được gọi là *literals*
- Hằng có thể thuộc bất kì dạng dữ liệu chuẩn nào và có thể phân chia thành số nguyên, dấu chấm động, kí tự, chuỗi và giá trị bool
- Hằng được xử lí như các biến thông thường chỉ có giá trị của chúng là không thay đổi 
### 3.1 Interger literals ( Kí tự nguyên)

<a name='kitunguyen'></a>

- Kí tự nguyên có thể là thập phân, bát phân hoặc thập lục phân. Tiền tố chỉ định cơ sở hoặc cơ số: 0x hay 0X cho cơ số 16, 0 cho cơ số 8 và không có gì cho cơ số 10
- Một kí tự nguyên cũng có thể có một hậu tố là một sự kệt hợp của U và L, cho *unsigned* và *long*. Hậu tố có thể là chữ hoa, chữ thường và có thể ở bất kì thứ tự nào
Ví dụ

```
212         // Legal
215u        // Legal
0xFeeL      // Legal
078         // Illegal: 8 is not an octal digit
032UU       // Illegal: cannot repeat a suffix
```
Nhiều dạng của kí tự nguyên

```
85         // decimal
0213       // octal
0x4b       // hexadecimal
30         // int
30u        // unsigned int
30l        // long
30ul       // unsigned long
```
### 3.2 Floating-point literals (Dấu chấm động)

<a name='dauchamdong'></a>

- Một dấu chấm động có một phần số nguyên, dấu chấm thập phân, một phần phân số và một phần số mũ. Bạn có thể đại diện dấu chấm động ở dạng thập phân hoặc dạng số mũ
- Khi đại diện ở dạng thập phân, bạn phải bao gồm dấu thập phân, số mũ hoặc cả hai. Khi đại diện ở dạng số mũ bạn phải bao gồm phần số nguyên, phần phân số hoặc cả hai. Chữ ký số được đại diễn bởi *e* hoặc *E*

```
3.14159       // Legal
314159E-5L    // Legal
510E          // Illegal: incomplete exponent
210f          // Illegal: no decimal or exponent
.e55          // Illegal: missing integer or fraction
```

### 3.3 Boolean literals

<a name='kitubool'></a>

- Có 2 dạng kí tự Boolean là `TRUE` và `FALSE`
- Không nên đặt giá trị **TRUE** là 1 và **FALSE** là 0

### 3.3 Character literals

<a name='kitu'></a>

- Kí tự là đính kèm với dấu ngoặc đơn. Nếu một kí tự bắt đầu với *L* (chỉ chữ hoa), nó là một kí tự rộng (ví dụ như L'x') được lưu trữ ở dạng `wchar_t`. Nếu không, nó là một kí tự chữ hẹp (ví dụ 'x') và được lưu trữ trong một biến đơn giản loại *char* 
- Một số kí tự trong C++ khi chúng được đánh dấu bằng dấu gạch chéo ngược, chúng sẽ mang nghĩa đặc biệt và được dùng để đại diện cho dòng mới (\n) hoặc tab (\t)
Một số danh sách có chức năng tương tự như vậy

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task03/Images/img3.PNG">

Ví dụ
```
#include <iostream>
using namespace std;
int main() {
   cout << "Hello\tWorld\n\n";
   return 0;
}
```

### 3.4 Kí tự chuỗi

<a name='kituchuoi'></a>

- Các kí tự chuỗi được đính kèo trong dấu ngoặc kép. Một chuỗi chứa các kí tự tương tự như là kí tự *character* 
- Có thể phá vỡ một dòng dài thành nhiều dòng bằng cách sử dụng *string literals* và tách bằng cách dùng khoảng trắng
Dưới đây là một số ví dụ. Cả 3 dạng đều giống nhau

```
"hello, dear"
"hello, \
dear"
"hello, " "d" "ear"
```
### 3.5 Defining Constants

