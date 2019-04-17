# Cấu trúc câu lệnh 
```
iptables -t (tên bảng) option
```

1. Check list các quy tắc hiện tại 
```
iptables -L
```
```
[root@localhost ~]# iptables -L
Chain INPUT (policy ACCEPT)
target     prot opt source               destination         
ACCEPT     all  --  anywhere             anywhere             stat
```
**NOTE** : các đọc bảng các quy tắc
- target :
- port : 
- source: 
- destination