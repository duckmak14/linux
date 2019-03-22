# Thay đổi đường dân đến file image 
- Khi tạo ra một VM thì sẽ đồng thời tạo ra 2 file là "xml" và "image" thì ở bài trước ta đã tìm hiểu về file XML thì có một đường dẫn tới file image. Bây giờ ta thử thay đổi đường dẫn tới file image của máy khác xem liệu chúng có còng hoạt động như bình thường
- Ta chuẩn bị 2 máy ảo đã được tạo ra và sửa file "xml" của chúng
- ![](https://github.com/duckmak14/linux/blob/master/KVM/images/XML_lab/screenshot_1.png)
- Ta sẽ sửa file xml máy 0-2 sang máy 0. Vào file xml và sửa dòng chỉ image tới của VM centos7.0
- ![](https://github.com/duckmak14/linux/blob/master/KVM/images/XML_lab/screenshot.png)
- Sau đó ta kiểm tra lại đường dẫn ở phần thông tin VM 
- ![](https://github.com/duckmak14/linux/blob/master/KVM/images/XML_lab/screenshot9.png)
- Khi đã chắc chắn thông tin đã được thay đổi thì sẽ ta sẽ chạy thứ máy ảo 
- ![](https://github.com/duckmak14/linux/blob/master/KVM/images/XML_lab/screenshot_10.png)
- Vậy là kết quả đã thấy rằng nó vẫn có thể chạy được
# Thay đổi card mạng bằng file "xml"
- Đâu tiên ta vào file xml của máy VM ta thấy kiểu mạng ở đây là NAT default 
- ![](https://github.com/duckmak14/linux/blob/master/KVM/images/XML_lab/screenshot6.png)
- Ta có thể kiểm tra ở mục mạng ở trong kvm 
- ![](https://github.com/duckmak14/linux/blob/master/KVM/images/XML_lab/screenshot_7.png)
- Hoặc ta có thể kiểm tra IP của nó 
- ![](https://github.com/duckmak14/linux/blob/master/KVM/images/XML_lab/screenshot_2.png)
- Sau đó ta thay đổi Kiểu mạng `default` thành `NAT-1` 
- ![](https://github.com/duckmak14/linux/blob/master/KVM/images/XML_lab/screenshot_4.png)
- Rồi ta kiểm tra xem có sự thay đổi thông tin của máy bằng ứng dụng virt-manager
- ![](https://github.com/duckmak14/linux/blob/master/KVM/images/XML_lab/screenshot_5.png)
### Vậy ta có thể thấy được rằng khi thay đổi card mạng bằng file XML thì kiểu mạng của VM cũng sẽ bị thay dổi theo 