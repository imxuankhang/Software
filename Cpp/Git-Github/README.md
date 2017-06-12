# Software
## Git-Github
> Võ Xuân Khang
Mục lục:

###  [1. Giới thiệu](#GioiThieu)
### [2. Thao tác cơ bản](#ThaoTac)

- #### [2. 0 Tạo Một repo](#Tao)

- #### [2. 1 Clone](#Clone)

- #### [2. 2 Add](#Add)
	
- #### [2. 3 Remove](#Remove)
	
- #### [2. 4 Commit ](#Commit)
	
- #### [2. 5 Push](#Push)
	
- #### [2. 6 Pull](#Pull)

- #### [2. 7 Remote](#Remove)

- #### [2. 8 Fork](#Fork)

- #### [2. 9 Star](#Star)

- #### [2. 10 Watch](#Watch)

- #### [2. 11 Fetch](#Fetch)

### [3. Cài đặt git, Generate, add key SHH...](#CaiDat)

- #### [3.1 Cài đặt Git](#CaiDatGit)

- #### [3.2 Các thiết lập ban đầu](#ThietLap)

- #### [3.3 Liên kết tài khoản github bằng SSH (Add key SSH) ](#AddKey)

- #### [3.4 Caching your Github password](#Caching)



### [4 Kết luận](#KetLuan)

---
<p name="GioiThieu"></p>
###  1. Giới thiệu về github

- Github là một dịch vụ lưu trữ dựa trên web cho các dự án phát triển phần mềm trong đó sử dụng các hệ thống kiểm soát phiên bản Git. Github cung cấp phiên bản trả phí cho các kho tư nhân, doanh nghiệp hoặc có thể miễn phí cho dự án mã nguồn mở. Github đang trở nên ngày càng phổ biến và thiết yếu hơn đối với các doanh nghiệp - như là một sơ yếu lý lịch cho các nhà tuyển dụng.

- Để sử dụng github, đầu tiên bạn [đăng ký](https://github.com/join?source=header-home) một tài khoản github và tất nhiên nó dể như ăn 1 tô cháo vậy. Sau đó có lẽ bạn nên học về ngôn ngữ Markdown (có thể không) để thể hiện rõ hơn cho bài viết của bạn và tất nhiên ngôn ngữ này cũng vô cùng đơn giản. Tiếp theo là tạo một repo và bắt đầu thôi.

- Tuy nhiên bạn nên hiểu sơ qua về cơ chế hoạt động của github
![](https://github.com/imxuankhang/Software/blob/master/Cpp/Git-Github/img/git1.png)

Như chúng ta đã thấy đó là những trạng thái của 1 repo github. Chúng ta sẽ nói sơ qua về các trạng thái còn những hành động tương ứng sẽ được bàn sau:

- __Working directory__: Là nơi chỉnh sửa file mã nguồn của mình, bạn có thể sử dụng bất kỳ editer nào để viết/code chúng
- __Stagging area__: Những thay đổi của bạn với file sẽ được lưu lại, giống như khi soạn file với gedit bạn nhấn Save vậy. 
- __Git directory__: Nơi lưu trữ mã nguồn của bạn (ở đây là github)

<p name="ThaoTac"></p>
###  2. Các thao tác cơ bản sử dụng github

<p name="Tao"></p>
#### 2. 1 Tạo Một repo

- Bạn vào github và chọn Create repository và điền thông tin vào
![](https://github.com/imxuankhang/Software/blob/master/Cpp/Git-Github/img/git5.png)

<p name="Clone"></p>
####  2. 2 Clone

- Để clone một repo về ta có thể chọn __Clone or Download__ và nhấn Download Zip hoặc copy đường dẫn (bạn có thể chọn clone sử dụng SSH hoặc HTTP) và thực hiện với lệnh sau:

	> git clone `đường dẫn vừa copy`    ` thư mục chứa repo trên local `

<p name="Add"></p>
####  2. 3 Add

- Để  thực hiện hành động `add` ta sử dụng lệnh sau:

	__git add "tên_file"__: 	dùng để `add` file chỉ định

	__git add *__ :		dùng để `add` tất cả

	__git add --all__	:	dùng để `add` tất cả

<p name="Remove"></p>	
####  2. 4 Remove	

- Để remove một thư mục hay một file nào đó bạn có thể xóa ở máy local sau đó add và commit lại là xong

- Nếu muốn xóa repo bạn vào repo đó trên server và chọn __Delete this repository__ ở phần Setting. Đọc warning và chọn yes...

<p name="Commit"></p>
####  2. 5 Commit 
	
- Để thực hiện hành động commit ta sử dụng lệnh sau:

	__git commit *__:	dùng để commit tất cả

	__git commit "tên_file" -m "thêm chú thích"__: 	dùng để thêm chú thích cho commit của mình

<p name="Push"></p>
####  2. 6 Push

- Sau khi commit thì tất cả đã lưu vào máy cục bộ và giờ thì chúng ta sẽ push lên server  với lệnh

	__git push -u origin master__:

	> Nhập passphrase nếu có

<p name="Pull"></p>
####  2. 7 Pull

- Hành động pull là hành động được thực hiện khi server có những thay đổi mà máy cục bộ vẫn chưa và giờ muốn cập nhật những thay đổi này. Ta dùng lệnh

	__git pull__: lưu ý vào đúng repo cần pull


<p name="Remove"></p>
#### 2. 8 Remote

- Việc remote được hiện khi bạn muốn add một máy chủ từ xa nào đó. Để thực hiện remote bạn làm như sau:

	> git remote add origin `'link repo'`

- Để liệt kê các remote mà bạn đã add thì có thể dùng lệnh 

	> git remote -v 


<p name="Fork"></p>
####  2. 9 Fork

- Tại một thời điểm ta muốn phân phối hay sử dụng một project hay repo của ai đó để bắt đầu và điều này nghĩa là ta sẽ Fork một repo về. Sau khi Fork về thì repo đó sẽ tồn tại trên github của chúng ta. Chúng ta có thể clone nó về máy local để bắt đầu sử dụng.

- Sau khi một repo được được clone, nó sẽ có một remote origin trỏ đến repo mà chúng ta đã Fork về chứ không phải là repo gốc. Để theo dõi repo gốc mà chúng ta đã Fork, chúng ta cần add một remote khác có tên là upstream:

	> git remote add upstream `link repo gốc`

	> git fetch upstream

<p name="Star"></p>
####  2. 10 Star

- Star một repo trong github như thể hiện cho việc repo này được nhiều người quan tâm, theo dõi. Đây cũng là cách để bạn tăng khả năng xuất hiện của repo mình trên github.

- Bạn có thể Star một repo bất kỳ và khi đó bạn có thể truy cập nhanh chóng và dể dàng theo dõi repo mà bạn quan tâm. Ngoài ra đây cũng là một sự đánh giá cho chủ nhân repo.

- Để thực hiện bạn chỉ cần nhấn vào Star trên repo đã chọn

<p name="Watch"></p>
####  2. 11 Watch

- Để thực hiện bạn chọn Watch trên repo mà bạn muốn và khi đó bạn sẽ nhận được thông báo cho các yêu cầu mới hay vấn đề gì xảy ra với repo đó.

<p name="Fetch"></p>
####  2. 12 Fetch

- Lệnh này sẽ truy cập vào dự án từ xa nào đó và cập nhật dữ liệu mà bạn chưa có trên repo đó. Sau khi Fetch xong bạn có thể tham chiếu đến toàn bộ các nhánh của dự án đó.

- Để thực hiện bạn sử dụng:

	> git fetch `tên remote`

	> Bạn có thể git fetch `upstream` như repo mà ta đã firk phía trên

<p name="CaiDat"></p>
###  3. Cài đặt git, Generate, add key SSH...

<p name="CaiDatGit"></p>
#### 3.1 Cài đặt Git

- Với HĐH là Ubuntu, Debian:

	> apt-get install git

- Với HĐH là Fedora, CentOS

	> yum install git

- Với Arch

	> pacman -S git

<p name="ThietLap"></p>
#### 3.2 Các thiết lập ban đầu

- Bạn cần thiết tập tên và email của mình để khi commit lên server sẽ nhận biết được ai đang commit lên1 repo (vì có thể nhiều người tham gia)
	> git config --global user.name "tên/username của bạn"

	> git config --global user.email "email của bạn"

- Lựa chọn trình soạn thảo mặc định (có thể không cần) như nano, vi, emacs,...
	> git config --global core.editor nano

- Bjna có thể xem lại các thiết lập của mình
	> git config --list

<p name="AddKey"></p>
#### 3.3 Liên kết tài khoản github bằng SSH (Add key SSH

- Bạn cũng có thể dùng lệnh sau để add key SSH 

> ssh-keygen -t rsa -C `email của bạn`

- Sau khi xong thì key rsa của bạn nằm ở ~/.ssh/
	
>	id_rsa		
>	id_rsa.pub 		
>	knowns_hosts

- Tiếp theo
	
![](https://github.com/imxuankhang/sysadmin_level1-1/blob/master/Task04_Git_and_Github/img/git2.png)

- Sau đó bạn copy đoạn mã trong file id_rsa.pub và truy cập đường dẫn https://github.com/settings/ssh và chọn New SSH key để thêm key vào (bạn nhớ là đăng nhập vào tài khoản github trước).

![](https://github.com/imxuankhang/Software/blob/master/Cpp/Git-Github/img/git3.png)

> Phần Title bạn ghi gì cũng được và phần key bạn paste đoạn mã lúc nãy vào. OK nhấn Add key

- Quay lại với terminal bạn có thể kiểm tra bằng cách đánh `ssh git@github.com` Nếu xuất hiện Hi username! You've successfully authenticated... thì chúc mừng bạn đã được liên kết với tài khoản github.

![](https://github.com/imxuankhang/Software/blob/master/Cpp/Git-Github/img/git4.png)

<p name="Caching"></p>
#### 3.4 Caching your Github password

- Nếu bạn clone repo sử dụng HTTP thì có thể sử dụng 1 helper để lưu user/pass tài khoản github để tiện việc commit những thay đổi (sẽ không cần đánh user/pass lại)

- Nếu bạn clone repo của github sử dụng SSH thì bạn sẽ xác thực bằng key SSH thay vì tên người dùng.

- Để sử dụng helper bạn dùng lệnh sau: 

	> git config --global credential.helper cache

	> git config --global credential.helper 'cache --timeout=1800'

> Lưu ý: nếu bạn không thiết lập thời gian cho helper thì mặc định sẽ là 15 phút

Sau khi đã liên kết được với github ta sẽ đi qua một vài thao tác cơ bản để hoạt động trên github sau

<p name="KetLuan"></p>
### 4. Kết luận

Trên đây mà cách cài đặt và sử dụng __cơ bản__ git và github. Bạn có thể tải và cài đặt git trên Windows và sử dụng bình thường.
