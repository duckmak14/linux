# 1.Khái niệm và Ứng dụng 
- linux bridge là một phần mềm được tích hợp vào trong nhân linux để giải quyết vấn đề ảo hóa phần network trong các máy vật lý.
- Linux bridge như là một con switch ảo để cho các VM kết nối được vào và ta có thể nói chuyện được với nhau và ra mạng ngoài. Ta thấy rằng con switch được tạo ra nằm bên trong của máy vậy lý.
- ![](https://github.com/niemdinhtrong/NIEMDT/blob/master/KVM/images/Linux-bridge/2.png)
- Chú ý: Ta không thể kết nổi switc ảo với card wireless do hệ điều hành không hỗ trợ
# 2. Cấu trúc của bridge 
- ![](https://github.com/niemdinhtrong/NIEMDT/blob/master/KVM/images/Linux-bridge/1.png)
- Tap: ta có thể hiểu được nó là một giao diện mạng để các máy ảo có thể giao tiếp được với bridge và nó nằm trong nhân kernel tap hoạt động ở lớp 2 trong mô hình OSI
- fd( forward data ): Dùng để chuyển tiếp data từ máy ảo 
- Bridge: là switch ảo là do linux bridge tạo ra nó có một số tính năng giống như switch vật lý
    - STP: là tính năng chống loop gói tin trong switch 
    - Tính năng tạo ra các vlan 
    - FDB: Là tính năng chuyển gói tin theo data-base để tăng tốc cho switch
    - 