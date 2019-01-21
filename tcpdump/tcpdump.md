# 1. Khái niệm 
- Tcpdum là phần mềm bắt gói tn trong mạng làm việc trên hầu hết các phiên bản hệ điều hành linux 
- Tcpdum cho phép bắt và lưu trữ những gói tin bắt được, từ đó chúng ta có thể sử dụng để phân tích
- Để sử dụng được tcpdump trên linux thì ta cần phải cài đặt 
- Với ubuntu 
```
sudo apt-get install tcpdump
```
- Đối với centos 
```
sudo yum install tcpdump
```
# 2. Tìm hiểu về một số câu lệnh của tcpdump
## 1.Hiển thị các giao diện mạng
Với option -D sẽ hiển thị ra danh sách các giao diện mạng có sẵn và ta có thể bắt các gói tin trên các giao diện này.
```
anhduc@anhduc:~$ tcpdump -D
1.wlp4s0 [Up, Running]
2.vmnet0 [Up, Running]
3.vmnet1 [Up, Running]
4.vmnet2 [Up, Running]
5.vmnet8 [Up, Running]
6.enp0s25 [Up, Running]
7.any (Pseudo-device that captures on all interfaces) [Up, Running]
8.lo [Up, Running, Loopback]
9.bluetooth0 (Bluetooth adapter number 0)
10.nflog (Linux netfilter log (NFLOG) interface)
11.nfqueue (Linux netfilter queue (NFQUEUE) interface)
12.usbmon1 (USB bus number 1)
13.usbmon2 (USB bus number 2)
14.usbmon3 (USB bus number 3)
15.usbmon4 (USB bus number 4)
```
## 2. Bắt gói tin từ một giao diện ethernet
Khi thực hiện lệnh tcpdump mà không có tùy chọn cụ thể nó sẽ bắt tất cả các gói tin đi qua tất cả các card mạng. Option -i cho phép lọc ra một interface ethernet cụ thể. Các interface ở đây là các interface mà là vừa liệt kê ở trên.




