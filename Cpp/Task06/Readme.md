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

