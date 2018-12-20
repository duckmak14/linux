# 1. Lệnh echo 
- Lệnh echo dùng để hiển thị một văn bản lên màn hình 
```
anhduc@anhduc:~$ echo text command
text command
```
- Ta có thể khai báo biến và lập lại giá trị của nó 
```
anhduc@anhduc:~$ x=10
anhduc@anhduc:~$ echo gia tri cua x=$x
gia tri cua x=10
```
- `-e` giúp nó hiểu được các ký tự có tác dụng đằng sau, ta có thể sử dụng nhiều trường đằng sau để kết hợp với nhau: như \b \n \t....
    - `\b` : dùng để loại bỏ 1 ký tự đằng trước nó 
    - `\n` : dùng để xuống dòng 
    - `\t` : dùng để cách một khoảng tab đằng trước 
    - `\v` : Xuống dòng và cách một khoảng trắng bằng các ký tự dòng trên 
    - `\r` : Xóa tất cả các ký tự trước đó 
    - `\c` : 
    ```
    anhduc@anhduc:~$ echo -e ' anh \c duc'
    anh anhduc@anhduc:~$ 
    ```
    - anhduc@anhduc:~$ echo *
        Desktop Documents Downloads examples.desktop Music nfs nfs-test Pictures PlayOnLinux's virtual drives pt Public scp snap Templates Videos vmware
    - `echo *(đuôi): in ra file có đuôi như thế
- Ta có thể gán giá trị cho ký tự được 
```
anhduc@anhduc:~$ echo "file" > a
anhduc@anhduc:~$ cat a
file
```
# 2.Lệnh cat
- Lệnh `cat` là lệnh dùng để đọc một file
- Lệnh cat có thể đọc nhiều file cùng một lúc 
```
anhduc@anhduc:~$ cat a b
file
file1
```
- Một số option của lệnh `cat`
    - `-n` để hiển thị từng dòng 
    ```
    anhduc@anhduc:~$ cat -n .bash_history 
     1	dhclient enp0s25
     2	sudo dhclient enp0s25
     3	vi /etc/network/interfaces
     4	ip a
     5	mtr 8.8.8.8
     6	ping dantri.vn 
     7	ip a
     8	sudo vi /etc/resolv.conf 
     9	ip a
    10	p a
    11	ip a
    12	ping dantri.vn 

    ```
    - `-e` để thêm ký tự $ vào cuối dòng 
    ```
    anhduc@anhduc:~$ cat -e a
    ile$
    ```
    - copy nội dung file này sang file khác 
    ```
    anhduc@anhduc:~$ cat a >> b
    anhduc@anhduc:~$ cat b
    file1
    file
    ```
    - Ghi đè file này lên file khác
    ```
    anhduc@anhduc:~$ cat a > b
    anhduc@anhduc:~$ cat b
    file
    ```
# 3. Lệnh Sed 
- Trong hệ điều hành linux thì `sed` được sử dụng rất nhiều.
- Đây là một trình soạn thảo văn bản. Khác với các văn bản thông thường `sed` chấp nhận văn bản dầu vào có thể là file trên hệ thống hay từ standard inpun và stdin
- sed sẽ dùng để chỉnh sửa từng dòng văn bản 
- Một số option 
    - `-n` ngăn chặn việc tự động in không gian mẫu
    - `-i` lưu thay đổi 
    - `-f` thêm nội dung của script-file vào các lệnh được thực thi 
    - `-i` Lưu thay đổi vào file vừa được thao tác
    - `/p` In ra vùng đã chỉ định 
### a) Thay thế một chuỗi ký tự
- Cấu trúc 
```
anhduc@anhduc:~$ echo anhduc | sed -e 's/anhduc/anh/'
anh 
```
- Trong đó
    - `s` : mô tả phép thay thế
    - Tất cả các chuỗi 1 được thay thế bằng chuỗi 2
    - tên file: là tên file ta muốn áp dụng sự thay thế
### b) Thay thế tất cả xuất hiện của mẫu 
- Nếu chỉ sử dụng mô tả `s` thì sự thay thế chỉ xảy ta ở mẫu đầu tiên. Nếu muốn thay thế tất cả sự xuất hiện của nó ở văn bản thì ta cần thêm `/g` ở cuối 
```
anhduc@anhduc:~$ echo anhducanhducanhducanhduc | sed -e 's/anhduc/anh/g'
anhanhanhanh
```

- Thay thế sự xuất hiện từ lần xuất hiện thứ 2 thì là 2g, thứ 3 là 3g...
```
anhduc@anhduc:~$ echo anhducanhducanhducanhduc | sed -e 's/anhduc/anh/2g'
anhducanhanhanh
```
- Thay thế sự xuất hiện của lần thứ n(1,2,3,4...)
```
anhduc@anhduc:~$ echo anhducanhducanhducanhduc | sed -e 's/anhduc/anh/2'
anhducanhanhducanhduc
```
### c) Xóa các dòng trống 
- Đọc file khi chưa sử dụng sed để kiểm tra các dòng trống 
- ![](https://github.com/duckmak14/linux/blob/master/text_commands/Screenshot%20from%202018-12-20%2015-29-53.png)
- Thực hiện lệnh sed
![](https://github.com/duckmak14/linux/blob/master/text_commands/Screenshot%20from%202018-12-20%2015-29-33.png)
### d)Kết hợp nhiều chuỗi lệnh sed 
```
anhduc@anhduc:~$ echo abc | sed 's/a/A/' | sed 's/b/B/'
ABc
anhduc@anhduc:~$ echo abc | sed 's/a/A/; s/b/B/'
ABc
```
- Hai cách viết trên cho kết quả giống nhau nhưng mà cách viết thứ 2 ngắn ngọn hơn 
### e) xóa các  dòng chứa 1 chuỗi bất kỳ trong file
- cấu trúc 
```
sed 's/[^.]*(ký tự )[^.]*//g' duc.txt
```
- ví dụ dưới đây là xóa dòng có ký tự `a`
- ![](https://github.com/duckmak14/linux/blob/master/text_commands/Screenshot%20from%202018-12-20%2015-36-38.png)
# 5. Grep 
- Lệnh `grep` : là lệnh được dùng để tìm kiếm 1 chuỗi ký tự ở trong file chỉ định 
### a) Tìm kiếm chuỗi trong file 
```
anhduc@anhduc:~/Desktop$ grep "a" duc.txt 
a
```
### b) Tìm nhiều chuỗi 
- ví dụ là tìm tất cả các chuỗi có ký  tự a ở trong file có đuôi `txt`
- ![](https://github.com/duckmak14/linux/blob/master/text_commands/Screenshot%20from%202018-12-20%2015-48-07.png)
### c) Tìm kiếm không phân biệt chữ hoa thường 
- Ta dùng option `-i`. Ví dụ tìm chuỗi có chưa ký tự `a`
- ![](https://github.com/duckmak14/linux/blob/master/text_commands/Screenshot%20from%202018-12-20%2015-50-27.png)
### d) Tìm kiếm chính xác với dòng chứa tất cả ký tự đó 
- Ta dùng option `-w`. Ví dụ tìm với chuỗi ký tự `a`
- ![](https://github.com/duckmak14/linux/blob/master/text_commands/Screenshot%20from%202018-12-20%2015-52-56.png)
### e) Hiện thị thêm những dòng xung quanh 
- Ta có các option là 
    - `-A` : là sau 
    - `-B` : là trước 
    - `-c` : xung quanh 
- cấu trúc 
```
grep -(A,B,C) (số dòng) "chuỗi" (tên file)
```
- ví dụ: 3 dòng trước ký tự a với tìm chính xác 
- ![](https://github.com/duckmak14/linux/blob/master/text_commands/Screenshot%20from%202018-12-20%2015-59-08.png)
###
