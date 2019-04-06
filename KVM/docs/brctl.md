## Khái niệm 
- `brctl` : Được dùng để tạo và thao tác với bridge ethernet 
## a) Hiển thị bridge ethernet có sẵn 
```
brctl show
```
## b) Tạo một bridge ethernet 
```
brctl addbr (tên bridge)
```
## c) Xóa một bridge ethernet 
```
brctl delbr (tên bridge)
```
## d) Thêm một if cho bridge 
```
brctl addif (tên bridge) (tên card)
```
## e) Xem địa chỉ MAC của bridge 
```
brctl showmacs prod 
```
## f) Thiết lập thời gian hết hạn cho bridge 
```
brctl setaging (tên bridge) (time (s))
```
- Nếu sau một khoảng thời gian time(s) mà không thấy được frame cho bridge thì địa chỉ MAC của client sẽ bị xóa cơ sở dữ liệu chuyển tiếp
