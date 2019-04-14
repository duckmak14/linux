# 1.Khái niệm 
iptables là gì : iptables là một gói phần mềm để tạo tường lửa cho máy linux của bạn nó có các chức năng lọc gói tin, nat gói tin qua đó để giúp làm nhiệm vụ bảo mật thông tin cá nhân tránh mất mát thông tin và áp dụng nhưng chính sách đổi với người sử dụng. 
# 2. Cấu trúc iptables
![]()

Bao gồm 3 thành phần chính: 
- Filter table 
- Nat table
- Mangle Table 

Chức năng của từng bảng 
## a) FILTER TABLE 
Trong bảng `filter` có những chain được xây dựng sẵn 
- Input chain: Đây là chain dùng đẻ lọc các gói tin đầu vào. Chain này là chain các gói tin bắt buộc phải đi qua để có thể được xử lý
- Output chain: đây là chain dùng để lọc các gói tin đầu ra. Sau khi gói tin được xử lý phải đi qua chain này để được ra ngoài
- Forward chain:  đây là chain dùng để chuyển gói tin qua lại giữa các card mạng với nhau
## b) Bảng NAT 