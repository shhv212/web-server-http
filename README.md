# Web server và HTTP

## Mục lục

[1. Web server là gì? Tìm hiểu về các loại web server hiện nay](#webserver)  
[2. Cơ chế hoạt động của web server](#cochehoatdong)  
[3. Tìm hiểu về giao thức HTTP](#http)  

==================================================

<a name="webserver"></a>  
# 1. Web server là gì? Tìm hiểu về các loại web server hiện nay

## Web server là gì?  

**Web server** là một loại máy chủ dùng để xử lý các yêu cầu từ phía người dùng thông qua trình duyệt web và gửi trả về bằng các file dữ liệu để hiển thị những nội dung như text, audio, video, ... Giao thức HTTP là giao thức chủ yếu để `web server` gửi và nhận thông tin từ các `web browser` của client.  

Chức năng cơ bản của `web server` là lưu trữ file thông tin và truyền dữ liệu tới các `web client` thông qua giao thức HTTP để người dùng có thể truy cập vào những website mà được cấu hình ở `web server`.  

Chúng ta chỉ cần cài đặt một phần mềm `Web Server Software` nào đó lên một máy tính bất kỳ là có thể biến nó trở thành một `Web server` khi được kết nối Internet. Những `web server` thực tế thường được sử dụng hiện nay để đáp ứng nhu cầu của người dùng sẽ phải hoạt động 24/24, nhờ đó ta có thể truy cập một trang web trên một máy tính bất kỳ ở trên mạng ở mọi lúc.  

## Các loại web server thông dụng hiện nay  

### Apache  

**Apache** là một phần mềm web server mã nguồn mở chiếm thị phần lớn trong lĩnh vực cung cấp các dịch vụ web server. Vì sử dụng giao thức HTTP để truyền tải thông và dữ liệu trên Internet nên nó còn có tên gọi đầy đủ là `Apache HTTP Server`. Đây cũng là một trong những nền tảng web server lâu đời nhất trên thế giới.  

### Nginx

**Nginx** là một trong những đối thủ cạnh tranh lớn của Apache và cũng là một phần mềm `web server` mã nguồn mở nổi tiếng. Nginx được ưu tiên sử dụng ở những website có traffic của dữ liệu lớn và yêu cầu khả năng lưu trữ và truy xuất tốc độ cao cùng với xử lý nhiều kết nối trong cùng một thời điểm.  \

###  IIS  

**IIS** là viết tắt của cụm từ `Internet Information Service`, là một `web server` được tích hợp trên Windows do Microsoft phát triển. Vì chỉ có thể chạy được trên Windows nên nó đặc biệt hỗ trợ tốt cho những ngôn ngữ và famework do Microsoft xây dựng và cập nhật.  

### Lighttpd

**Lighttpd** là một phần mềm `web server` mã nguồn mở rất nhẹ và tiêu tốn cực kì ít tài nguyên của hệ thống. Hiện nay, nó đang phát triển mạnh và được ưa chuộng bởi cộng đồng công nghệ vì nó là giải pháp càn thiết cho mọi server về vấn đề tải trọng.  

<a name="cochehoatdong"></a>  
# 2. Cơ chế hoạt động của web server  

<img src="https://i.imgur.com/FTalNiP.png">  

Khi chúng ta gõ tên một trang web vào trình duyệt thì sau đó trang web này sẽ được hiển thị trên màn hình. Giải thích cho vấn đề đó, ta có đầu tiên khi gõ tên trang web thì DNS server sẽ trả về địa chỉ IP tương ứng với domain name đó, nhưng còn 2 phần nữa cũng quan trọng gắn với tên miền là tên giao thức được sử dụng để giao tiếp với web server và tập tin cấu hình của trang web cần truy cập.  
Ví dụ chúng ta có một địa chỉ website như sau : http://abc.com/index.php lên trên browser, ngay lập tức browser sẽ lọc ta các phần tương ứng, tên giao thức sử dụng là `http`, domain name là `abc.com` và tên file được yêu cầu là `index.php`(file này chứa tất cả nội dung của trang web). Sau đó trình duyệt web ở client sẽ gửi yêu cầu tới DNS server để truy vấn địa chỉ IP tương ứng mà ta đã biết, có được địa chỉ IP rồi thì tiếp tục gởi một yêu cầu để kết nối tới `web server` tại địa chỉ IP đó với port 80. Lúc này browser sẽ dùng phương thức GET của giao thức HTTP để lấy một file có tên là `index.php` từ chính `web server`. Browser dùng file này để load trang web hiển thị lên màn hình.  

<a name="http"></a>  
# 3. Tìm hiểu giao thức HTTP  

**HTTP** được viết tắt là `Hypertext Transfer Protocol`, chính là giao thức truyền tải dữ liệu được sử dụng chủ yếu trong mạng Internet giữa các `Web server` và các trình duyệt web ở Client. HTTP bao gồm các chức năng được thiết kế để giao tiếp trong mô hình `Client-Server`. Khi chúng ta truy cập một website nào đó tức là đang có một kết nối giữa Client và Web server thông qua địa chỉ IP mà máy chủ DNS cung cấp. Web server sau khi nhận các yêu cầu từ trình duyệt web sẽ trả về các lệnh giúp hiển thị website và các thông tin liên quan khác.  

**HTTP** có những đặc điểm cơ bản như nó là một giao thức không liên tục, sau khi `client` kết nối tới `server` bằng giao thức HTTP thì trình duyệt web tạo ra một yêu cầu trang web nào đó tới `server`, lúc đó thì kết nối sẽ bị ngắt để `client` chờ phản hồi từ `server` và khi mà `server` xử lý xong yêu cầu thì sẽ thiết lập lại kết nối để gửi dữ liệu cho `client`; khi mà thiết lập được kết nối thì cả 2 bên có thể gửi cho nhau tất cả các loại dữ liệu, mà 2 bên chỉ cần có thể xử lý được nó và sau khi hoàn tất phiên làm việc đó thì cả `client` và `server` đều không lưu thông tin của yêu cầu đó.  

Hiện nay do nhu cầu bảo mật trên mạng lưới Internet ngày càng tăng của người dùng và sự tấn công của hacker ngày càng nguy hiểm cũng như mức độ tổn thất rất lớn, do đó các kỹ sư IT đã cải tiến giao thức HTTP bằng cách tích hợp các Chứng chỉ SSL hoặc TLS vào để nó trở nên an toàn hơn gọi tên là giao thức `HTTPS`, nói một cách dễ hiểu thì `HTTPS` là phiên bản nâng cấp hơn của `HTTP` về độ tin cậy.  

<img src="https://i.imgur.com/ntSjuXr.png">  

Vì tính bảo mật của nó nên các website hiện nay ưu tiên sử dụng giao thức `HTTPS` hơn, nhằm bảo vệ thông tin của chính mình cũng như gia tăng sự tin tưởng của người dùng. Vì phải trải qua các bước xác minh những Chứng chỉ yêu cầu nên tốc độ truy cập của `HTTPS` sẽ chậm hơn so với `HTTP` tuy nhiên với công nghệ tiên tiến hiện tại thì tốc độ hơn kém nhau không đáng kể.


