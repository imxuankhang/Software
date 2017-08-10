# Task05

> Thực hiện: Võ Xuân Khang

## Mục lục:

[1. C++ Functions (Hàm)](#ham)

[1.1 Defining a Function](#defining)

[1.2 Function Declarations](#declaration)

[1.3 Calling a Function](#calling)

[1.4 Function Arguments](#arguments)

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

[4.1 The C-Style Character Strings](#characters_string)

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

- Để sử dụng một hàm, bạn phải gọi hàm đó
- Khi chương trình gọi hàm, chương trình điều khiển sẽ truyền đến hàm được gọi. Hàm có thể trả về giá trị là giá trị của câu lệnh **return()** hoặc không trả về giá trị nào nếu như *return type* là **void()**
Ví dụ:
```
#include <iostream>
using namespace std;
 
// function declaration
int max(int num1, int num2);
 
int main () {
   // local variable declaration:
   int a = 100;
   int b = 200;
   int ret;
 
   // calling a function to get max value.
   ret = max(a, b);
 
   cout << "Max value is : " << ret << endl;
 
   return 0;
}
 
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
Hàm *max()* được giữ lại cùng với hàm **main()** đến cuối chương trình và khi kết thúc chương trình sẽ cho ra kết quả như sau:
`Max value is : 200`

### 1.4 Function Arguments

<a name='arguments'></a>

- Khi gọi một hàm, có 2 cách mà đối số có thể được truyền đến một hàm

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task05/Images/IMG1.PNG">

- Mặc định, C++ sử dụng *call by type* hay truyền tham trị để truyền đối số. Nói chung, điều này có nghĩa là code trong hàm không thể thay đổi đối số được sử dụng để gọi hàm và ví dụ được đề cập ở trên khi gọi hàm *max()* được sử dụng cùng phương pháp 
- Ngoài truyền tham trị còn có 2 cách truyền đối số khác là tham chiếu và sử dụng con trỏ

### 1.5 Default Values for Parameters

<a name='default_values'></a>

- Bạn có thể chỉ định một giá trị mặc định cho mỗi tham số, giá trị này sẽ được sử dụng nếu đối số tương ứng để trống khi gọi hàm
- Điều này được thực hiện bằng cách sử dụng toán tử gán (gán giá trị cho đối số trong hàm). Nếu giá trị cho đối số không được truyền khi hàm được gọi thì giá trị mặc định sẽ được sử dụng. Nhưng nếu đối số được truyền giá trị thì giá trị mặc định sẽ được bỏ qua không dùng. 
Ví dụ:
```
#include <iostream>
using namespace std;
 
int sum(int a, int b=20) {
   int result;

   result = a + b;
  
   return (result);
}

int main () {
   // local variable declaration:
   int a = 100;
   int b = 200;
   int result;
 
   // calling a function to add the values.
   result = sum(a, b);
   cout << "Total value is :" << result << endl;

   // calling a function again as follows.
   result = sum(a);
   cout << "Total value is :" << result << endl;
 
   return 0;
}
```
Kết quả
```
Total value is :300
Total value is :120
```

## 2. Numbers in C++

<a name='number'></a>

Thông thường, khi làm việc với số, ta thường sử dụng các dạng dữ liệu truyền thống như **int, short, long, float...** 

### 2.1 Defining Numbers in C++

<a name='defining'></a>

- Dưới đây là ví dụ của các loại số khác nhau trong C++
```
#include <iostream>
using namespace std;
 	
int main () {
   // number definition:
   short  s;
   int    i;
   long   l;
   float  f;
   double d;
   
   // number assignments;
   s = 10;      
   i = 1000;    
   l = 1000000; 
   f = 230.47;  
   d = 30949.374;
   
   // number printing;
   cout << "short  s :" << s << endl;
   cout << "int    i :" << i << endl;
   cout << "long   l :" << l << endl;
   cout << "float  f :" << f << endl;
   cout << "double d :" << d << endl;
 
   return 0;
}
```
Kết quả:
```short  s :10
int    i :1000
long   l :1000000
float  f :230.47
double d :30949.4
```

### 2.2 Math Operations in C++

<a name='toan_tu'></a>

- Ngoài các hàm tự tạo, C++ cũng bao gồm một số hàm hữu dụng mà ta có thể sử dụng. Một số hàm có sẵn trong thư viện chuẩn C/C++ và được gọi là hàm xây dựng sẵn.
- C++ có một tập các toán tử số học phong phú. Dưới đây là các hàm toán tử số học có sẵn 
- Để sử dụng các hàm này ta cần khai báo thư việc **<cmath>**

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task05/Images/IMG2.PNG">
Ví dụ:
```
#include <iostream>
#include <cmath>
using namespace std;
 					
int main () {
   // number definition:
   short  s = 10;
   int    i = -1000;
   long   l = 100000;
   float  f = 230.47;
   double d = 200.374;

   // mathematical operations;
   cout << "sin(d) :" << sin(d) << endl;
   cout << "abs(i)  :" << abs(i) << endl;
   cout << "floor(d) :" << floor(d) << endl;
   cout << "sqrt(f) :" << sqrt(f) << endl;
   cout << "pow( d, 2) :" << pow(d, 2) << endl;
 
   return 0;
}
```
Kết quả:
```
sign(d) :-0.634939
abs(i)  :1000
floor(d) :200
sqrt(f) :15.1812
pow( d, 2 ) :40149.7
```

### 2.3 Random Numbers in C++

<a name='random_numbers'></a>

- Trong nhiều trường hợp, ta sẽ cần sử dụng những số được lựa chọn tùy ý. Có 2 hàm hỗ trợ cho việc này đó là **rand()** và **srand()**
- Dưới đây là ví dụ đơn giản

```
#include <iostream>
#include <ctime>
#include <cstdlib>

using namespace std;
 
int main () {
   int i,j;
 
   // set the seed
   srand( (unsigned)time( NULL ) );

   /* generate 10  random numbers. */
   for( i = 0; i < 10; i++ ) {
      // generate actual random number
      j= rand();
      cout <<" Random Number : " << j << endl;
   }

   return 0;
}
```

Kết quả:

```
 Random Number : 1748144778
 Random Number : 630873888
 Random Number : 2134540646
 Random Number : 219404170
 Random Number : 902129458
 Random Number : 920445370
 Random Number : 1319072661
 Random Number : 257938873
 Random Number : 1256201101
 Random Number : 580322989
```

## 3. C++ Arrays

<a name='mang'>

- C++ cung cấp một cấu trúc dữ liệu gọi là mảng, mảng chứa các phần tử cùng loại. 
- Thay vì khai báo từng biến như so0, so1, so2,....,so99; ta khai báo một mảng *so[100]* và sử dụng tuần tự các chỉ số [0],[1],...,[99] để biểu diễn. Một biến trong mảng được truy xuất bởi một tên mảng đi kèm với chỉ số của biến đó. Mảng bao gồm các địa chỉ bộ nhớ liên tiếp. Phần tử đầu có địa chỉ thấp nhất, phần tử cuối có địa chỉ cao nhất

### 3.1 Declaring Arrays

<a name='declaring'></a>

- Để khai báo một mảng, ta dùng cú pháp sau:
`type arrayName [arraySize];`
- *arraySize* phải lớn hơn 0 và *type* là các dạng dữ liệu cho phép bởi C++. Chỉ số trong mảng được đánh dấu bắt đầu từ 0

### 3.2 Initializing Arrays

<a name='initializing'></a>

- Bạn có thể khởi tạo từng giá trị một trong mảng
Ví dụ

```
balance[5]=50.0;
```

Hoặc cũng có thể khởi tạo giá trị từ lúc khai báo mảng như sau

```
double balance[] = {1000.0, 2.0, 3.4, 7.0, 50.0};
```

Số giá trị trong dấu {} phải vừa khớp với giá trị trong trường *arraySize*. Nếu ta để giá trị trong dấu [] là trống thì mảng sẽ khởi tạo ra số phần tử bằng với số giá trị mà ta khởi tạo
- Dưới đây là biểu diễn hình ảnh của một mảng

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task05/Images/IMG3.PNG">

### 3.3 Accessing Array Elements

<a name='accessing'></a>

- Như đã nói ở trên các phần tử trong mảng được truy xuất bằng cách *arrayName[stt]*
Ví dụ:

 `double salary = balance[5];`

Câu lệnh trên sẽ lấy phần tử thứ 6 và gán cho biến *double salary* 
- Ví dụ dưới đây sử dụng tất cả các khái niệm đã nói ở trên

```
#include <iostream>
using namespace std;
 
#include <iomanip>
using std::setw;
 
int main () {
   int n[ 10 ]; // n is an array of 10 integers
 
   // initialize elements of array n to 0          
   for ( int i = 0; i < 10; i++ ) {
      n[ i ] = i + 100; // set element at location i to i + 100
   }
	
   cout << "Element" << setw( 13 ) << "Value" << endl;
 
   // output each array element's value                      
   for ( int j = 0; j < 10; j++ ) {
      cout << setw( 7 )<< j << setw( 13 ) << n[ j ] << endl;
   }
 
   return 0;
}
```
Chương trình trên có sử dụng hàm **setw()** để định dạng đầu ra. Và đây là kết quả

```
Element        Value
      0          100
      1          101
      2          102
      3          103
      4          104
      5          105
      6          106
      7          107
      8          108
      9          109
```

### 3.4 C++ Arrays in Detail

<a name='detail'></a>

- Mảng rất quan trọng trong hầu hết các ngôn ngữ lập trình. Có một số khái niệm sau cần nắm rõ

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task05/Images/IMG4.PNG">

- Mảng đa chiều: ví dụ đơn giản nhất là mảng 2 chiều
- Con trỏ đến một mảng: có thể tạo ra một con trỏ trỏ tới vị trí đầu tiên trong mảng bằng cách chỉ định tên mảng mà không cần chỉ mục nào
- Truyền mảng đến hàm: có thể truyền con trỏ của hàm đến một mảng bằng cách xác định tên mảng mà không cần chỉ mục nào
- Trả lại mảng từ hàm: C++ cho phép hàm trả về một mảng

## 4. C++ Strings

<a name='chuoi'></a>

- C++ cung cấp 2 kiểu trình bày chuỗi như sau:
	- Chuỗi theo phong cách của ngôn ngữ C
	- Lớp chuỗi được giới thiệu trong C++ chuẩn

### 4.1 The C-style character strings

<a name='characters_string'></a>

- Dạng này bắt nguồn từ ngôn ngữ lập trình C và tiếp tục được hỗ trỡ trong C++. Chuỗi thực chất là mảng một chiều của các ký tự mà kết thúc bởi ký tự **null** '\0'
- Dưới đây khai báo và khởi tạo một chuỗi bao gồm một từ "hello". Kích thước của mảng các kí tự bao gồm một chuỗi phải nhiều hơn số lượng các ký tự trong từ khóa "hello" để giá trị **null** tồn tại

`char greeting[6] = {'H','e','l','l','o','\0'};`

- Nếu bạn sử dụng chuỗi, bạn có thể viết như sau:

`char greeting[] = "Hello";`

- Dưới đây là phần biểu diễn ô nhớ cho đoạn chuỗi trong C/C++

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task05/Images/IMG5.PNG">

- Trên thực tế, trình biên dịch C++ sẽ tự động thêm '\0' vào vị trí cuối cùng của chuỗi khi nó khởi tạo mảng. Hãy thử in chuỗi trên:

```
#include <iostream>

using namespace std;

int main () {
   char greeting[6] = {'H', 'e', 'l', 'l', 'o', '\0'};

   cout << "Greeting message: ";
   cout << greeting << endl;

   return 0;
}
```

Kết quả:

`Greeting message:Hello`

- C++ hỗ trợ nhiều hàm đa dạng để thao tác các chuỗi kết thúc là null

<img src="https://github.com/imxuankhang/Software/blob/master/Cpp/Task05/Images/IMG6.PNG">

Ví dụ:
```
#include <iostream>
#include <cstring>

using namespace std;

int main () {
   char str1[15] = "Hello";
   char str2[15] = "World";
   char str3[15];
   int  len ;

   // copy str1 into str3
   strcpy( str3, str1);
   cout << "strcpy( str3, str1) : " << str3 << endl;

   // concatenates str1 and str2
   strcat( str1, str2);
   cout << "strcat( str1, str2): " << str1 << endl;

   // total lenghth of str1 after concatenation
   len = strlen(str1);
   cout << "strlen(str1) : " << len << endl;

   return 0;
}
```
Kết quả:
```
strcpy( str3, str1) : Hello
strcat( str1, str2): HelloWorld
strlen(str1) : 10
The String 
```

### 4.2 The String Class in C++

<a name='string_class'></a>

- Thư viện chuẩn C++ cung cấp một kiểu lớp **string** hỗ trợ tất cả các hoạt động liên quan đến chuỗi như trên và bổ sung thêm một số chức năng. Chúng ta sẽ học lớp này trong bài **Thư viện chuẩn C++** nhưng bây giờ hãy cùng nhau kiểm tra ví dụ sau:
- Tại thời điểm này, bạn có thể không hiểu ví dụ trên vì cho đến nay chúng ta chưa thảo luận về **Classes and Objects (Lớp và Đối tượng)**. Vì vậy bạn quan sát và ghi nhớ nó tới khi bạn đã hiểu các khái niệm về Hướng đối tượng được trình bày ở những bài học sau

```
#include <iostream>
#include <string>

using namespace std;

int main () {
   string str1 = "Hello";
   string str2 = "World";
   string str3;
   int  len ;

   // copy str1 into str3
   str3 = str1;
   cout << "str3 : " << str3 << endl;

   // concatenates str1 and str2
   str3 = str1 + str2;
   cout << "str1 + str2 : " << str3 << endl;

   // total lenghth of str3 after concatenation
   len = str3.size();
   cout << "str3.size() :  " << len << endl;

   return 0;
}
```
 
Kết quả khi thực thi: 
 
 ```
 str3 : Hello
 str1 + str2 : HelloWorld
 str3.size() :  10
 ```

