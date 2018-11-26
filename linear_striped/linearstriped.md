# 1 Khái niệm 
- Linear và striped là tên của hai loại, kiểu ghi dữ liệu vào ổ cứng khi tao dùng kỹ thuật LVM
- Phân biệt giữa linear và striped
- ![](https://assets.sysadmincasts.com/e/g/27-linear-vs-striped-logical-volume-overview.png)
- giả sử ta phải ghi vào một dữ liệu vào các ổ cứng thì cách ghi dữ liệu của hai kiểu sẽ như trên hình
    - Linear: sẽ lưu dữ liệu vào từng phân vùng hết phân vùng này đến phân vùng khác 
    - Striped: sẽ chia đều các dữ liệu ra và ghi vào các phân vùng đã có. Và cách chia dữ liệu ra bao nhiêu thì được định sẵn bởi người cài đặt nó
# 2. Cách cài đặt 
a) Linear
- Để cài đặt được `linear logical volume` trước tiên ta phải có `group volume` mà nó chưa cấp cho `logical volume` nào cả. 
- Sau đó ta dùng lệnh `lvcreate --extenes (số %)FREE --name (tên logical)
- ![](https://github.com/duckmak14/linux/blob/master/linear_striped/Screenshot%20from%202018-11-26%2010-11-48.png)
