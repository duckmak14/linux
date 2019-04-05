# 1. Tổng quan về giao thức DHCP 
a) Khái niệm về giao thức DHCP 
-   DHCP(Dynamic Host Configuration Protocol) : Là một giao thức cấp phát địa chỉ IP ; subnet mask; default gateway; dịch vụ DNS ( giao thức cấu thình host động)
- Nó thường được cấp phát bởi DHPC server tích hợp trên router 

b) Đặc điểm DHCP 
- Làm việc theo mô hình Client/Server 
- Giao thức DHCP sử dụng port 68 và port 67 
- Ưu điểm khi sử dụng DHCP
    - Tập trung quản trị thông tin cấu hình I
    - Cấu hình động các máy
    - Cấu hình IP cho các máy một cách liền mạch.
    - Sự linh hoạt
    - Khả năng mở rộng.
    - Đơn giản hóa vài trò quản trị của việc cauas hình địa chỉ IP của client.
c) Kiến trúc DHCP 
- Có 3 thành phần bên trong kiến trúc DHCP bao gồm DHCP client, DHCP server, và DHCP relay agents
    - DHCP client: Là thiết bị dùng để kết nối vào mạng.
    - DHCP server: Là thiết bị cấp phát địa chỉ
    - DHCP relay agents: Là thiết bị trung gian chuyển tiếp giữa 2 thiết bị trên
- Một địa chỉ IP được cấp sẽ sử dụng được tối đa 24h. Sau Khi sử dụng địa chỉ IP 24h thì nó sẽ tự động đổi địa chỉ IP mới cho host 
d) Quá trình cấp IP của giao thức DHCP 
- Bước 1: Client tạo bản tin DHCPDISCOVER
Ban đầu, Client chưa có địa chỉ IP và nó có thể biết hoặc không biết vị trú của DHCP server trong mạng. Để tìm DHCP server, nó tạo bản tin DHCP DISCOVER: Địa chỉ MAC; có thể yêu cầu một địa chỉ IP xác định.
- Bước 2: Client gửi bản tin DHCP DISCOVER dưới dạng broadcast
- Bước 3: Server nhận và xử lý bản tin DHCP DISCOVER. Nó sẽ kiểm tra IP nào đã được sử dụng. Và chọn ra IP để cấp cho client 
- Bước 4: Server tạo bản tin DHCP OFFER. Gói tin này sẽ lưu trữ thông tin về IP và các thông số cấu hình khác mà client yêu cầu để có thể sử dụng để truy cập internet
- Bước 5: Tất cả các server sẽ gửi bản OFFER dưới dạng broadcast.
- Bước 6: Client nhận gói OFFER và nó sẽ chọn ra bản OFFER đầu tiên mà nó nhận được. Nếu không nhận được OFFER nào trong một khoảng thời gian nào đó thì nó sẽ gửi lại DISCOVER một lần nữa 
- Bước 7: Client tạo ra gói REQUEST. Và gửi dưới dạng broadcast tới tất cả các server. Server nào được nhận OFFER sẽ mang ý nghĩa là nó đồng ý nhận IP. Server nào không được nhận OFFER thì thông báo là không nhận OFFER đó
- Bước 8: Server nhận bản tin REQEST. Các server không được nhận OFFER sẽ bỏ qua gói tin này. Gói tin nào được nhận OFFER sẽ nhận và xử lý nó. Nó sẽ kiểm tra sem IP này còn sử dụng được hay không. Nếu còn sử dụng được thì nó sẽ ghi lại thông tin và gửi lại gói tin PACK cho client. Còn nếu không thì nó sẽ gửi lại PNAK để quay lại bước 1.
# 2.DHCP trong KVM
- Như phần trên thì ta cũng đã tìm hiểủ về DHCP là dịch vụ cấp phát địa chỉ IP động. Vậy trong KVM sự khác nhau giữa kiểu mạng là mô hình của nó. Và để chưng minh được sự khác nhau đó thì ta chứng minh rằng nơi cấp DHCP cho VM để thấy rõ được sự khác biệt giữa 2 kiểu mạng Bridge và NAT. 
## a) DHCP trong kiểu mạng NAT
- 