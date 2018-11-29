# 1.Khái niệm
- `fdisk` là một lệnh được sử dụng để xem và quản lý các phân vùng ổ cứng trên linux. Nó là một trong những công cụ tốt nhất để có thể quản lý phân vùng ổ cứng. 
- Lưu ý:
    - khi dùng `fdisk` thì nó sẽ xóa hết dữ liệu trong phân vùng. thế nên khi dùng lệnh `fidsk` chú ý sao lưu dữ liệu quan trọng lại rồi mới tiến hành dùng lệnh 
    - Bạn không thể di chuyển các ứng dụng từ phân vùng này qua phân vùng khác mà không gỡ cài đặt.
# 2. Một số option của lệnh fdisk
- `fdisk -l`: giúp ta liệt kê các danh sách phân vùng của ổ cứng 
- `lsblk` cũng giống như lệnh `fdisk -l` nhưng nó chỉ liệt kê chứ không hiển thị ít thông tin hơn `fdisk -l`
- `fdisk /dev/sda`: đây là lệnh giúp ta bước vào ổ đĩa và bắt đầu làm việc với các phân vùng trong ổ đĩa  
    - Sau khi vào được bên trong ổ đĩa thì các bước làm việc như tạo một phân vùng xóa phân vùng đã được viết ở trong bài LVM 
- `fdisk -l /dev/sda`: chỉ kiểm tra phân vùng của riêng ổ đĩa sda 
- `fdisk -s /dev/sda1` : lệnh kiểm tra size của phan vùng 
- `fdisk -v` : hiển thị thông tin phiên bản 
