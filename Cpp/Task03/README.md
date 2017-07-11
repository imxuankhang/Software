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

[3.6 Defining Constants](#xacdinhhang)

[3.7 The #define preprocessor](#define)

[3.8 The const Keyword](#key-const)

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

<a name='dinhnghiahang'></a>

Có 2 cách để xác định hằng
- Sử dụng `#define`
- Sử dụng từ khóa `const`

#### 3.5.1 Sử dụng **#define**

<a name='define'></a>

Có dạng

`#define identifier value`

Ví dụ

```
#include <iostream>
using namespace std;
#define LENGTH 10
#define WIDTH 5
#define NEWLINE '\n'
int main()
{
	int area;
	area=LENGTH * WIDTH;
	cout << area;
	cout <<NEWLINE;
	return 0;
}
```

#### 3.5.2 Sử dụng từ khóa **const**

<a name='key-const'></a>

Có dạng
`const type variable = value;`

Ví dụ

```
#include <iostream>
using namespace std;
int main()
{
	const int LENGTH = 10;
	const int WIDTH = 5;
	const char NEWLINE = '\n';
	int area;
	area = LENGTH * WIDTH;
	cout << area;
	cout << NEWLINE;
	return 0;
}
```

### 4. Modifier Types

<a name='bonghia'></a>

- C++ cho phép các kiểu dữ liệu như **char,int, double** có các bổ nghĩa trước nó. Bổ nghĩa được sử dụng để thay đổi ý nghĩa của các loại kiểu dữ liệu cơ sở để nó phù hợp hơn với nhu cầu của các tình huống khác nhau
- Các bổ nghĩa của các kiểu dữ liệu được liệt kê dưới đây
 - **signed**
 - **unsigned**
 - **long**
 - **short**
- Kiểu bổ nghĩa **signed, unsigned, long, short** có thể áp dụng cho kiểu số nguyên. Ngoài ra, **signed, unsigned** có thể áp dụng cho kiểu **char** và **long** có thể áp dụng cho **double**
- Bổ nghĩa **signed, unsigned** cũng có thể sử dụng như tiền tố của **long** hoặc **short**
VD: `unsigned long int`
- C++ cho phép viết tắt để khai báo **unsigned, short, long** cho số nguyên. Bạn có thể sử dụng từ đơn như **unsigned, short, long** với kiểu **int**, kiểu **int** được ngụ ý. 

```
unsigned x;
unsigned int y;
```
- Chương trình dưới đây giúp ta hiểu được sự khác biệt giữa bổ nghĩa **signed** và **unsigned** số nguyên

```
#include <iostream>
using namespace std;
 
/* This program shows the difference between
 * signed and unsigned integers.
*/
int main() 
{
   short int i;           // a signed short integer
   short unsigned int j;  // an unsigned short integer

   j = 50000;
   i = j;
   cout << i << " " << j;
   return 0;
}
```
Sau khi chạy, chương trình sẽ có kết quả

`-15536 50000`

* Kết quả trên là vì mẫu bit đại diện *50000* ở kiểu **short unsigned int** được giải thích như *-15536* ở kiểu **short** *

- Các dạng vòng cung cấp thông tin bổ sung cho các biến mà nó đứng trước

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task03/Images/img4.PNG">



