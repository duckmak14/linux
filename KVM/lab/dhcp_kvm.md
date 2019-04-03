# 1. Tổng quan về giao thức DHCP 
a) Khái niệm về giao thức DHCP 
-   DHCP(Dynamic Host Configuration Protocol) : Là một giao thức cấp phát địa chỉ IP ; subnet mask; default gateway; dịch vụ DNS ( giao thức cấu thình host động)
- Nó thường được cấp phát bởi DHPC server tích hợp trên router 
b) Kiến trúc DHCP 
- Có 3 thành phần bên trong kiến trúc DHCP bao gồm DHCP client, DHCP server, và DHCP relay agents
    - DHCP client: Là thiết bị dùng để kết nối vào mạng.
    - DHCP server: Là thiết bị cấp phát địa chỉ
    - DHCP relay agents: Là thiết bị trung gian chuyển tiếp giữa 2 thiết bị trên
- Một địa chỉ IP được cấp sẽ sử dụng được tối đa 24h. Sau Khi sử dụng địa chỉ IP 24h thì nó sẽ tự động đổi địa chỉ IP mới cho host 
# 2.DHCP trong KVM
- Như phần trên thì ta cũng đã tìm hiểủ về DHCP là dịch vụ cấp phát địa chỉ IP động. Vậy trong KVM sự khác nhau giữa kiểu mạng là mô hình của nó. Và để chưng minh được sự khác nhau đó thì ta chứng minh rằng nơi cấp DHCP cho VM để thấy rõ được sự khác biệt giữa 2 kiểu mạng Bridge và NAT. 
## a) DHCP trong kiểu mạng NAT
- 