## Markdown

> Võ Xuân Khang

### Mục lục.

[1. Markdown là gì?]

-[1.1 Gioi thiệu](#gioithieu)
-[1.2 Markdown dùng để làm gì?](#tacdung)

[2. Cú pháp](#cuphap)

[3. Cài đặt Subline Text, tìm kiếm cài đặt các Packet hỗ trợ Markdown](#sublinetext)

[4.Công cụ Editor](#congcu)

[5.Kết luận](#ketluan)

-----------------------

###1. Markdown là gì?

<a name='gioithieu'></a>

####1.1 Gioi thiệu

Năm 2004, cùng với sự giúp đỡ của [Aaron Swarts](https://vi.wikipedia.org/wiki/Aaron_Swartz) John Gruber đã tạo ra ngôn ngữ markdown với mục tiêu tạo ra một định dạng văn bản thô dễ viết, dễ đọc, dễ dàng chuyển thành XHTML(hoặc HTML)

<a name='tacdung'></a>

####1.2 Markdown dùng để làm gì

Mardown thường được dùng để:
- Tạo ra các tập tin README, wiki cho các dự án mã nguồn mở trên github, họ cũng dùng để comment (hỗ trợ trên nhiều trang web, diễn đàn)
- Markdown còn dùng để viết sách, truyện với các thành phần cơ bản.
- Markdown còn dùng để viết blog, tin tức như chính mục tiêu ban đầu của tác giả.
- Ngoài ra có thể kết hợp với impress.js thành một công cụ presentation vô cùng độc đáo là Hekyll

<a name='cuphap'></a>

###2. Cú pháp

Markdown sử dụng khá đơn giản với một số cú pháp dễ nhớ. tuy nhiên chúng có nhiều cách viết có thể cho những nơi khác nhau như github, blog như đã nói ở trên. Chúng ta sẽ tìm hiểu qua 1 vài cú pháp cơ bản
> Còn rất nhiều [cú pháp khác](https://daringfireball.net/projects/markdown/syntax) chưa được đề cập đến.

####2.1 Headers(thẻ tiêu đề)

Markdown sử dụng kí tự # để bắt đầu cho các thẻ tiêu đề (có thể dùng từ 1 kí tự # đến 6 kí tự #)

vd: `# Tiêu đề cấp 1`
	Kết quả: 
	# Tiêu đề cấp 1


	`###### Tiêu đề cấp 6`
	Kết quả:
	######  Tiêu đề cấp 6

####2.2 Chèn link,ảnh

- Để chèn link ta chỉ cần dán link đó vào là được `https://github.com`

	Kết quả: https://github.com

	Hoặc rút ngắn với cú pháp như sau `[github](https://github.com)`

	Kết quả: 
	[github](https://github.com)

- Để chèn ảnh có 2 cách

	- Chèn trực tiếp qua link bằng cách `<img src="link">` hoặc `![chú_thích](link)`
	> Hình ảnh bạn có thể lấy bất cứ đâu trên internet, có thể bạn up lên để lấy link (có thể up lên http://i.imgur.com/)

	- Hoặc chèn bằng cách `![chú_thích](/đường dẫn)`

####2.3 In đậm, in nghiêng từ

- Để in đậm sử dụng `**Từ cần in đậm**` hoặc `__Từ cần in đậm__`
	vd: **AAA**

- Để in nghiêng sử dụng `*từ cần in nghiêng*`
	vd: *AAA*

####2.4 Gạch đầu dòng

Để gạch đầu dòng sử dụng

`
- Gạch đầu dòng 1
<ul>
<li> Thụt đầu dòng lần 1 </li>
</ul>
- Gạch đầu dòng 2
<ul>
<li>Thụt đầu dòng lần 1 </li>
</ul>
`
 
Hoặc dùng **Enter** và __Tab__ như sau:

`
- Gạch đầu dòng 1
	- Thụt đầu dòng lần 1
- Gạch đầu dòng 2
 	- Thụt đầu dòng lần 1
`

 	Kết quả:
 	- Gạch đầu dòng 1
 		- Thụt đầu dòng lần 1
 	- Gạch đầu dòng 2
 		- Thụt đầu dòng lần 1

 ####2.5 Chú thích cuối trang

 Chú thích `[^1]` `[^2]`

 	Kết quả: [^1] Chú thích 1
 ####2.6 Chèn bảng

  `
  |Cột 1 |Cột 2|Cột 3|
  |------|-----|-----|
  |hàng 2|2x2  |2x3  |
  |hàng 3|3x2  |3x3  |
  `
  `
  Kí tự bắt đầu 1 hàng hoặc cột: |
  Kí tự tách thành header: -
  `

  Kết quả:  |Cột 1 |Cột 2|Cột 3|
  			|------|-----|-----|
  			|hàng 2|2x2  |2x3  |
  			|hàng 3|3x2  |3x3  |

####2.7 Tạo điểm nhấn

Để tạo điểm nhấn dùng cặp == ==
 
Kết quả: ==AAA==

####2.8 Chèn code

`
``` code
printf("AAA");
```
`
Kết quả:	``` code
			printf("AAA");
			```
####2.9 Trích dẫn

Dùng cặp dấu `` hoặc `````` để tạo trích dẫn

Kết quả `Khang`

<a name="sublinetext"></a>

###3. Cài đặt subline text. Tìm kiếm cài đặt các công cụ hỗ trợ Markdown

Các bạn dowload **Subline Text** tại đường dẫn https://www.sublimetext.com/3. Cài đặt sau đó click vào tùy chọn *install package* như hình https://github.com/imxuankhang/Software/blob/master/Cpp/Markdown/img/img1.png sau đó tìm kiếm các công cụ và install

<a name="congcu"></a>

### 4. Các công cụ thường dùng
Chúng ta có thể sử dụng bất kỳ trình soạn thảo nào như sublime, notepad, remarkable... để viết Markdown với đuôi file là **.md**. Bạn có thể viết Markdown online qua các trang web sau:

- https://stackedit.io/editor
- https://jbt.github.io/markdown-editor/
- http://www.tablesgenerator.com/markdown_tables
- https://markable.in/editor/

> Chúng ta có thể chuyển sang các định dạng khác như HTML trực tiếp với các công cụ trực tuyến này.

<a name="ketluan"></a>

###5. Kết luận

#### Ưu điểm.
Đây là một ngôn ngữ cơ bản dễ dùng giúp ta có thể sử dụng rất nhiều nơi với cú pháp cơ bản. Có lẽ đây là ưu điểm lớn nhất của Markdown.
#### Nhược điểm.
Nhược điểm lớn nhất của Markdown có lẽ là khả năng cộng tác trong Markdown và theo giỏi những thay đổi. Vì đơn giản nên chỉ có thể dùng cho các dự án nhỏ lẻ, bài blog và tất nhiên những dự án lớn hay những quyển sách cần nhiều hơn những thứ mà Markdown hỗ trợ.