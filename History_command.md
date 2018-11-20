# 1. Lý thuyết 
a) Khái niệm 
- `history` là câu lệnh giúp ta hiển thị danh sách các lệnh đã sử dụng trong linux
- Muốn kiểm tra xem lệnh `history` có thể hiển thị bao nhiêu lệnh thì ta có `echo $HISTSIZE`
# 2.Thực hành Các option 
- ` | grep (tên cần tìm kiếm)` : option này giúp ta tìm kiếm từ hoặc dòng lệnh giống với tổ hợp phím `Ctrl+R`
- `| tail` : hiển thị mười lệnh cuối cùng 
- `| less` : hiển thị command đã thực hiện theo trang 
- Hiển thị số lệnh cuối cùng `history (số command)`
- `-c` : Dùng để xóa lịch sử 
- `!số` : Thực hiện lệnh thứ bao nhiêu ở trong lịch sử nhớ
# 3. Vấn đề mở rộng 
a) Mặc định history ghi lại được bao nhiêu command đã thực hiện, có thể thay đổi được không? Thay đổi như nào?
- Mặc định history ghi lại được 1000 command đã thực hiện 
- Có thể sửa được số dòng command hiển thị ta vào sửa file bash_profile
b) Kiểm tra một command được thực hiện bởi user nào và lúc nào?
- Để kiểm tra một user thao tác lệnh ta có thể làm được bằng cách đọc file lịch sử của user đó
- Để có thể biết được thời gian thao tác lệnh của một user thì ta có cách để đọc lệnh cùng với time thực hiện nó
