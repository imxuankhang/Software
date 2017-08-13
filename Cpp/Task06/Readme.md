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

[5. C++ Data Structures(cấu trúc)](#cautruc)

[5.1 Defining a Structure(định nghĩa)](#dinhnghia)

[5.2 Accessing Structure Members(truy cập thành viên)](#truycapthanhvien)

[5.3 Structures as Function Arguments(cấu trúc dưới dạng tham số hàm)](#cautrucduoidangthamsoham)

[5.4 Pointers to Structures(con trỏ đến cấu trúc)](#controdencautruc)

[5.5 The typedef Keyword(từ khóa **typedef**)](#tukhoatypedef)

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
 
 - Một biến tham chiếu là một **alias**, đó là cái tên khác cho biến đã tồn tại. Khi một tham chiếu được khởi tạo với một biến thì hoặc tên biến hoặc tên tham chiếu có thể được sử dụng để tham chiếu tới biến đó.

### 2.1 Tham chiếu và con trỏ trong C++

<a name='thamchieu&contro'></a>

- Tham chiếu thường bị nhầm lẫn với con trỏ. Nhưng có 3 sự khác biệt lớn giữa tham chiếu và con trỏ là:
	- Không có tham chiếu NULL. Bạn phải luôn giả định rằng một tham chiếu được kết nối với một phần của bộ nhớ
	- Khi một tham chiếu được khởi tạo cho mọt đối tượng, nó không thể thay đổi để chỉ đến một đối tượng khác. Con trỏ có thể trỏ đến một đối tượng khác bất kì lúc nào
	- Một tham chiếu phải được khởi tạo khi nó được tạo ra. Các con trỏ có thể được khởi tạo bất kì lúc nào

### 2.2 Tạo tham chiếu trong C++

<a name='tao'></a>

- Xem một tên biến như là một label(nhãn) được đính kèm với vị trí bộ nhớ. Sau đó, ta xem tham chiếu như là nhãn thứ hai được đính kèm với vị trí bộ nhớ đó. Qua đó, ta có thể truy cập nội dung của biến thông qua 2 cách: tên biến bao đầu hoặc tham chiếu. Như ví dụ sau:

`int i = 19;`

Ta có thể khai báo biến tham chiếu cho i như sau:

`int& r = i;`

Dấu & trong các khai báo này là tham chiếu. Vì vậy, trong khai báo đầu tiên, *r* là tham chiếu kiểu interger khởi tạo cho *i*

- Ví dụ:
```
#include <iostream>
 
using namespace std;
 
int main () {
   // declare simple variables
   int    i;
   double d;
 
   // declare reference variables
   int&    r = i;
   double& s = d;
   
   i = 5;
   cout << "Value of i : " << i << endl;
   cout << "Value of i reference : " << r  << endl;
 
   d = 11.7;
   cout << "Value of d : " << d << endl;
   cout << "Value of d reference : " << s  << endl;
   
   return 0;
}
```
Trong khai báo thứ 2, *s* là tham chiếu double được khởi tạo cho *d*. Khi biên dịch và chạy code trên ta được kết quả
```
Value of i : 5
Value of i reference : 5
Value of d : 11.7
Value of d reference : 11.7
```

- Tham chiếu thường được sử dụng cho danh sách các đối số của hàm và hàm trả về giá trị. Vì vậy dưới đây là 2 đối tượng quan trọng liên quan đến tham chiếu C++:

<img src = "https://github.com/imxuankhang/Software/blob/master/Cpp/Task06/Images/IMG2.PNG">

## 3. C++ Date and Time

<a name='date&time'></a>

- Thư viện chuẩn C++ không cung cấp một kiểu dữ liệu *date* phù hợp. C++ kế thừa các cấu trúc và hàm cho thao tác *date/time* từ C. Để truy cập các hàm và cấu trúc liên quan đến *date/time*, ta cần khai báo **include<ctime>** tại tiêu đề của chương trình C++
- Có 4 kiểu liên quan đến thòi gian: **clock_t, time_t, size_t** và **tm**. Trong đó **clock_t,time_t,size_t** có thể biểu diễn ngày và giờ hệ thống ở dạng **int**
- Kiểu cấu trúc **tm** giữ ngày và giờ ở dạng cấu trúc C có các phần tử sau:

```
struct tm {
   int tm_sec;   // seconds of minutes from 0 to 61
   int tm_min;   // minutes of hour from 0 to 59
   int tm_hour;  // hours of day from 0 to 24
   int tm_mday;  // day of month from 1 to 31
   int tm_mon;   // month of year from 0 to 11
   int tm_year;  // year since 1900
   int tm_wday;  // days since sunday
   int tm_yday;  // days since January 1st
   int tm_isdst; // hours of daylight savings time
}
```

- Dưới đây là các hàm quan trọng mà ta sử dụng trong khi làm việc với ngày và giờ trong C/C++. Tất cả các hàm này là một phần của thư viện chuẩn C/C++ và ta có thể kiểm tra chi tiết chúng bằng cách sử dụng tham chiếu đến thư viện C++ dưới đây

<img src = "https://github.com/imxuankhang/Software/blob/master/Cpp/Task06/Images/IMG3.PNG">

### 3.1 Date và Time hiện tại

<a name='current'></a>

Gỉa sử bạn muốn lấy date và time hệ thống hiện tại. Hay giờ địa phương hoặc giờ hợp nhất (UTC). Sau đây là ví dụ để đạt được điều trên:

```
#include <iostream>
#include <ctime>

using namespace std;

int main( ) {
   // current date/time based on current system
   time_t now = time(0);
   
   // convert now to string form
   char* dt = ctime(&now);

   cout << "The local date and time is: " << dt << endl;

   // convert now to tm struct for UTC
   tm *gmtm = gmtime(&now);
   dt = asctime(gmtm);
   cout << "The UTC date and time is:"<< dt << endl;
}
```
Kết quả

```
The local date and time is: Sat Jan  8 20:07:41 2011

The UTC date and time is:Sun Jan  9 03:07:41 2011
```

### 3.2 Định dạng Time sử dụng cấu trúc tm struct trong C++

<a name='dinhdang'></a>

- Cấu trúc **tm** là rất quan trọng khi làm việc với ngày và giờ trong C/C++. Cấu trúc này giữ ngày và giờ trong mẫu của một cấu trúc C như đã đề cập ở trên. Hầu hết các hàm liên quan đến thời gian đều sử dụng cấu trúc này. Dưới đây là ví dụ sử dụng đa dạng các hàm liên quan đến ngày và giờ và cấu trúc **tm**
- Khi sử dụng cấu trúc trong chương này, hãy giả sử các bạn đã hiểu cơ bản về cấu trúc trong C và cách truy cập các thành viên của cấu trúc bằng cách sử dụng toán tử *->*

```
#include <iostream>
#include <ctime>

using namespace std;

int main( ) {
   // current date/time based on current system
   time_t now = time(0);

   cout << "Number of sec since January 1,1970:" << now << endl;

   tm *ltm = localtime(&now);

   // print various components of tm structure.
   cout << "Year" << 1900 + ltm->tm_year<<endl;
   cout << "Month: "<< 1 + ltm->tm_mon<< endl;
   cout << "Day: "<<  ltm->tm_mday << endl;
   cout << "Time: "<< 1 + ltm->tm_hour << ":";
   cout << 1 + ltm->tm_min << ":";
   cout << 1 + ltm->tm_sec << endl;
}
```

Kết quả

```
Number of sec since January 1, 1970:1294548238
Year: 2011
Month: 1
Day: 8
Time: 22: 44:59
```

## 4. C++ Basic Input/Output

<a name='input&output'></a>

- Thư viện chuản C++ cung cấp nhiều khả năng input/output và sẽ được thấy trong các chương tiếp theo. Chương này sẽ thảo luận các hoạt động I/O cơ bản nhất và phổ biến được yêu cầu cho lập trình C++
- I/O trong C/C++ diễn ra trong các Stream(dòng) - đó là dãy các bye. Nếu các byte truyền từ một thiết bị như bàn phím, ổ đĩa hoặc một kết nối mạng...đến bộ nhớ chính, thì điều này được gọi là hoạt động đầu vào và nếu các byte truyền từ bộ nhớ chính tới một thiết bị như màn hình, máy in, ổ đĩa hay kết nối mạng...thì được gọi là hoạt động đầu ra...

### 4.1 Header file cho I/O

<a name='headerfile'></a>

<img src = "https://github.com/imxuankhang/Software/blob/master/Cpp/Task06/Images/IMG4.PNG">

### 4.2 Standard Output Stream trong C++(cout)

<a name='cout'>

- Đối tượng được xác định trước **cout** là một thể hiện của lớp **ostream** dùng để kết nối với thiết bị đầu ra chuẩn (thường là màn hình). **cout** được sử dụng kết hợp với toán tử chèn, được viết bằng << như ví dụ sau:

```
#include <iostream>
 
using namespace std;
 
int main( ) {
   char str[] = "Hello C++";
 
   cout << "Value of str is : " << str << endl;
}
```
Sau khi biên dịch và chạy chương trình sẽ được kết quả sau
```
Value of str is : Hello C++
```

- Trình biên dịch C++ cũng xác định kiểu dữ liểu của biến để được output và chọn toán tử chèn thích hợp để hiển thị giá trị. Toán tử << được nạp chồng (overload) tới dữ liệu đầu ra kiểu *integer, float, double, string* và giá trị con trỏ có sẵn
- Toán tử chèn << có thể được sử dụng nhiều hơn một lần trong một câu lệnh như hiển thị ở trên và **endl** được sử dụng để thêm một dòng mới tại cuối dòng đó

### 4.3 Standard Input Stream trong C++(cin)

<a name='cin'></a>

- Đối tượng được xác định trước **cin** là một thể hiện của lớp **istream** dùng để đính kèm đến thiết bị đầu vào chuẩn (như bàn phím). **Cin** được sử dụng kết hợp với toán tử trích dẫn >> như ví dụ sau
```
#include <iostream>
 
using namespace std;
 
int main( ) {
   char name[50];
 
   cout << "Please enter your name: ";
   cin >> name;
   cout << "Your name is: " << name << endl;
 
}
```

Khi biên dịch và thực thi chương trình trên, nó sẽ nhắc bạn chèn *name*. Khi bạn chèn *name* và nhấn enter sẽ được kết quả sau
```
Please enter your name: cplusplus
Your name is: cplusplus
```

- Trình biên dịch C++ cũng xác định kiểu dữ liệu của biến được chèn và chọn toán tử trích dẫn thích hợp đễ trích giá trị và lưu trữ nó trong các biến đã cung cấp 
- Toán tử trích >> cũng được sử dụng nhiều hơn một lần trong một câu lệnh. Để yêu cầu nhiều hơn một dữ liệu chuẩn, ta có thể sử dụng
`cin >> name >> age;`
Điều này tương đương với câu sau
```
cin >> name;
cin >> age;
```

### 4.3 Standard Error Stream trong C++(cerr)

<a name='cerr'></a>

- Đối tượng xác định trước **cerr** là một thể hiện của lớp **ostream** dùng để đính kèm đến thiết bị báo lỗi chuẩn, cũng là màn hình nhưng đối tượng **cerr** không được đệm và mỗi dòng chèn vào **cerr** sẽ xuất ra ngay lập tức
- **Cerr** cũng được sử dụng kết hợp với toán tử chèn như ví dụ sau đây:
```
#include <iostream>
 
using namespace std;
 
int main( ) {
   char str[] = "Unable to read....";
 
   cerr << "Error message : " << str << endl;
}
```
Kết quả
`Error message : Unable to read....`

### 4.4 Standard Log Stream trong C++(clog)

<a name='clog'></a>

- Đối tượng xác định trước **clog** là một thể hiện của lớp **ostream** được xem như đính kèm với thiết bị lỗi chuẩn, cũng là màn hình hiển thị nhưng đối tượng **clog** là được đệm. Nghĩa là mỗi sự chèn tới **clog** làm đầu ra được giữ lại trong bộ đệm *buffer* tới khi bộ đệm đầy hoặc khi bộ đệm bị flush (chuyển từ đệm ra đĩa)
- Đối tượng **clog** trong C++ cũng sử dụng kết hợp với toán tử chèn, như ví dụ sau:
```
#include <iostream>
 
using namespace std;
 
int main( ) {
   char str[] = "Unable to read....";
 
   clog << "Error message : " << str << endl;
}
```
Kết quả
`Error message : Unable to read.....`

- Bạn không thấy bất kì điểm khác nhau nào giữa **cout,cin,cerr,clog** với những ví dụ nhỏ này. Nhưng trong khi viết và thực thi các chương trình lớn, thì sự khác nhau này trở nên rõ ràng hơn. Vì thế, nó là bài thực hành tốt cho bạn để hiển thị thong báo lỗi sử dụng **cerr** và khi hiển thị các thông báo log khác, thì **clog** nên được sử dụng

## 5. C++ Data Structures(cấu trúc)

<a name='cautruc'></a>

- Các mảng trong C/C++ cho phép bạn giữ giáp trị của một vài thành viên cùng kiểu dữ liệu. Nhưng structure - cấu trúc là một loại dữ liệu khác trong ngôn ngữ lập trình C/C++, cho phép bạn kết hợp các kiểu dữ liệu khác nhau
- Các cấu trúc được sử dụng để biểu thị một bản ghi, giả sử muốn lưu trữ giá trị của một quyển sách trong thư viện. Ta có thể lưu trữ các thuộc tính của sách sau:
	- Tiêu đề
	- Tác giả
	- Chủ đề
	- Book ID

[5.1 Defining a Structure(định nghĩa)](#dinhnghia)
- Để định nghĩa một cấu trúc, bạn phải sử dụng câu lệnh **struct**. Câu lệnh struct định nghĩa một kiểu dữ liệu mới, với hơn một thành viên trong chương trình của bạn. Định dạng của câu lệnh struct như sau:
```
struct [structure tag] {
   member definition;
   member definition;
   ...
   member definition;
} [one or more structure variables];  
```

- "structure tag" có thể tùy chọn và một thành viên định nghĩa là các biến thường định nghĩa như int i, float j hay một định nghĩa biến khác. Tại phần cuối của định nghĩa cấu trúc, trước dấu chấm phẩy, bạn nên xác định một hay nhiều biến cấu trúc(tùy chọn). Ví dụ sau là khai báo cấu trúc Book
```
struct Books {
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
}book;  
```

5.2 Accessing Structure Members(truy cập thành viên)

<a name='truycapthanhvien'></a>

- Để truy cập bất kì thành viên nào của một cấu trúc, chúng ta dùng toán tử truy cập phần tử (.). Toán tử truy cập phần tử là mã hóa là dấu chấm giữa tên biến cấu trúc và phần tử cấu trúc muốn truy cập. Ta phải sử dụng từ khóa **struct** để định nghĩa dạng biến của cấu trúc. Dưới đây là ví dụ cho cách sử dụng cấu trúc trong C++
```
#include <iostream>
#include <cstring>
 
using namespace std;
 
struct Books {
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
};
 
int main( ) {
   struct Books Book1;        // Declare Book1 of type Book
   struct Books Book2;        // Declare Book2 of type Book
 
   // book 1 specification
   strcpy( Book1.title, "Learn C++ Programming");
   strcpy( Book1.author, "Chand Miyan"); 
   strcpy( Book1.subject, "C++ Programming");
   Book1.book_id = 6495407;

   // book 2 specification
   strcpy( Book2.title, "Telecom Billing");
   strcpy( Book2.author, "Yakit Singha");
   strcpy( Book2.subject, "Telecom");
   Book2.book_id = 6495700;
 
   // Print Book1 info
   cout << "Book 1 title : " << Book1.title <<endl;
   cout << "Book 1 author : " << Book1.author <<endl;
   cout << "Book 1 subject : " << Book1.subject <<endl;
   cout << "Book 1 id : " << Book1.book_id <<endl;

   // Print Book2 info
   cout << "Book 2 title : " << Book2.title <<endl;
   cout << "Book 2 author : " << Book2.author <<endl;
   cout << "Book 2 subject : " << Book2.subject <<endl;
   cout << "Book 2 id : " << Book2.book_id <<endl;

   return 0;
}
```

Khi biên dịch ta được kết quả như sau
```
Book 1 title : Learn C++ Programming
Book 1 author : Chand Miyan
Book 1 subject : C++ Programming
Book 1 id : 6495407
Book 2 title : Telecom Billing
Book 2 author : Yakit Singha
Book 2 subject : Telecom
Book 2 id : 6495700
```

5.3 Structures as Function Arguments(cấu trúc dưới dạng tham số hàm)

<a name='cautrucduoidangthamsoham'></a>

- Bạn có thể truyền một cấu trúc như một tham số hàm theo cách tương tự như bạn truyền biến hay con trỏ. Bạn nên truyền biến cấu trúc theo cách tương tự như bạn truyền trong ví dụ ở trên
```
#include <iostream>
#include <cstring>
 
using namespace std;
void printBook( struct Books book );

struct Books {
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
};
 
int main( ) {
   struct Books Book1;        // Declare Book1 of type Book
   struct Books Book2;        // Declare Book2 of type Book
 
   // book 1 specification
   strcpy( Book1.title, "Learn C++ Programming");
   strcpy( Book1.author, "Chand Miyan"); 
   strcpy( Book1.subject, "C++ Programming");
   Book1.book_id = 6495407;

   // book 2 specification
   strcpy( Book2.title, "Telecom Billing");
   strcpy( Book2.author, "Yakit Singha");
   strcpy( Book2.subject, "Telecom");
   Book2.book_id = 6495700;
 
   // Print Book1 info
   printBook( Book1 );

   // Print Book2 info
   printBook( Book2 );

   return 0;
}

void printBook( struct Books book ) {
   cout << "Book title : " << book.title <<endl;
   cout << "Book author : " << book.author <<endl;
   cout << "Book subject : " << book.subject <<endl;
   cout << "Book id : " << book.book_id <<endl;
}
```

Khi biên dịch và thực thi sẽ cho kết quả như dưới đây:
```
Book title : Learn C++ Programming
Book author : Chand Miyan
Book subject : C++ Programming
Book id : 6495407
Book title : Telecom Billing
Book author : Yakit Singha
Book subject : Telecom
Book id : 6495700
```

5.4 Pointers to Structures(con trỏ đến cấu trúc)

<a name='controdencautruc'></a>

- Ta có thể định nghĩa con trỏ đến cấu trúc theo cách tương tự như ta định nghĩa con trỏ đến biến bất kì
`struct Books *struct_pointer;`

- Bây giờ, ta có thể lưu trữ địa chỉ của biến cấu trúc trong định nghĩa biến con trỏ ở trên. Để tìm địa chỉ của biến cấu trúc, đặt toán tử & trước tên cấu trúc như sau:
`struct_pointer = &Book1;`

- Để truy cập phần tử của cấu trúc sử dụng con trỏ đến cấu trúc này, bạn phải sử dụng toán tử -> như dưới đây
`struct pointer -> title;`

- Giờ ta hãy thử viết lại ví dụ ở trên bằng cách sử dụng con trỏ cấu trúc
```
#include <iostream>
#include <cstring>
 
using namespace std;
void printBook( struct Books *book );

struct Books {
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
};
 
int main( ) {
   struct Books Book1;        // Declare Book1 of type Book
   struct Books Book2;        // Declare Book2 of type Book
 
   // Book 1 specification
   strcpy( Book1.title, "Learn C++ Programming");
   strcpy( Book1.author, "Chand Miyan"); 
   strcpy( Book1.subject, "C++ Programming");
   Book1.book_id = 6495407;

   // Book 2 specification
   strcpy( Book2.title, "Telecom Billing");
   strcpy( Book2.author, "Yakit Singha");
   strcpy( Book2.subject, "Telecom");
   Book2.book_id = 6495700;
 
   // Print Book1 info, passing address of structure
   printBook( &Book1 );

   // Print Book2 info, passing address of structure
   printBook( &Book2 );

   return 0;
}

// This function accept pointer to structure as parameter.
void printBook( struct Books *book ) {
   cout << "Book title : " << book->title <<endl;
   cout << "Book author : " << book->author <<endl;
   cout << "Book subject : " << book->subject <<endl;
   cout << "Book id : " << book->book_id <<endl;
}
```

Kết quả
```
Book title : Learn C++ Programming
Book author : Chand Miyan
Book subject : C++ Programming
Book id : 6495407
Book title : Telecom Billing
Book author : Yakit Singha
Book subject : Telecom
Book id : 6495700		
```

5.5 The typedef Keyword(từ khóa **typedef**)

<a name='tukhoatypedef'></a>

- Có một cách dễ dàng hơn để định nghĩa một cấu trúc. Ví dụ:
```
typedef struct {
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
}Books;
```

- Bây giờ ta có thể sử dụng *Books* một cách trực tiếp để định nghĩa các biến của kiểu cấu trúc *Books* mà không sử dụng từ khóa **struct**. Ví dụ:
`Books Book1, Book2;`

- Ta có thể sử dụng từ khóa **typedef** cho các dạng không phải cấu trúc, như sau:
```
typedef long int *pint32;
pint32 x,y,z;
```
x,y và z là tất cả con trỏ trỏ tới kiểu *long int*
 