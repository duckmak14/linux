Centos 7 dùng để làm gì?
-	Nó là hệ điều hành có mã nguồn mở
-	Thường dùng để chạy web, cơ sở dữ liệu…..

Tại sao lại dùng centos 7 mà không dùng các hệ điều hành khác? Điểm nổi bật của nó?
-	Nó là hệ điều hành chạy theo kiểu sever
-	Nhẹ hơn và bảo mật hơn 

Hệ thống người dùng ở trong centos 7 gốm 2 loại:
-	Root ( là tài khoản có quyền cao nhất trong hệ thống) 
-	User
Để thao tác với hệ thống người dùng thì phải đứng ở bên root.

Tất cả thông tin của root và user đều  được lưu trong một file để kiểm tra file thì dùng câu lệnh

Cat	/ etc/group: thông tin về các tài khoản root

Cat: mở file 

Etc/group: tên file

Cat	/etc/passwd

Clear: xóa màn hình 

Để tạo ra một group : groupadd (tên group)

VỀ USER

Một group có thể chứa nhiều user và một user có thể thuộc nhiều group

Một user có thể thuộc tối đa 17 group : 1 primary group và 16 secondary group 

Để tạo ra một user: useradd ( tên user

Khi tạo ra một user thì nó sẽ được mặc định cấp cho 1 thư mục trong home

Kiểm tra xem có bao nhiêu user : ls –l

Khi tạo ra một user thì sẽ có 1 group mặc định được tao ra cùng tên với user 

Kiểm tra user thuộc group nào: groups (tên user)

Đổi pass user: passwd (tên user)

Các tham số để thay đổi thông tin

-c thêm thông tin cho user 

-d thư mục đăng nhập mới của người dùng. Nếu kết hợp với –m thì nội dung thư mục chính của user sẽ được chuyển vào lưu trữ tại thư mục mới này 

-a thêm user vào các group khác chỉ sử dụng  cho –G

-e thêm vào ngày mà tài khoản sẽ bị vô hiệu hóa 

-f cài đặt số ngày tài khoản bị vô hiệu hóa sau khi mật khẩu hết hạn

-g thay đổi primary group của user 

-G thêm secondary group  cho user 

-l thay đổi tên user 

-L khóa mật khẩu user 

-m di chuyển đến vị chí mới 

-u tạo một id mới cho user  

-o cho phép thêm một giá trị nếu dùng với –u thì  sẽ thêm một id mới 

-U mở khóa mật khẩu user khi chưa bị hết hạn 





