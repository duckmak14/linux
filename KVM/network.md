- Cũng giống như các công cụ ảo hóa khác thì KVM cũng cung cấp các mô hình mạng trong việc ảo hóa network. Các mô hình mạng bao gồm 
    - NAT
    - Bridge
    - Router network
# 1. NAT
![]()
- NAT networking thường được cung cấp và kích hoạt theo mặc định bởi hầu hết các bản phân phối linux chính hỗ trợ ảo hóa KVM
- Mặc định một switch mạng ảo vận hành trong chế độ NAT mode sử dụng IP ảo. Điều này dẫn đến bất kì máu ảo nào được kết nối tới nó sử dụng địa chỉ IP của máy host để liên lạc ra bên ngoài và các máy bên ngoài không thể liên lạc được máy guest ở trong khi mà swtich họat động ở chế độ `NAT`
- Nó cho phép hệ điều hành khách có thể kết nối ra ngoài được mà không cần yêu cầu cấu hình cụ thể 
- Chế độ này coi Libvirt server như một router 
- Đây sẽ là chế độ mặc định khi mới cái libvirt mà không cần cấu hình gì 
### Cách cấu hình mạng NAT 
- Khi cài KVM thì ta sẽ được cung cấp một mạng ảo NAT là `default` 
- Mạng này thường mang dỉa địa chỉ IP 192.168.122.X Nếu không dùng mạng ảo `default thì ta có thể tạo ra một mô hình NAT khác có một vài cách để thực hiện nó. 
- Sử dung công cụ `Virtual Machine Manager`
    - Vào edit chọn connection details
    - 
# 2. Bridged 
- 