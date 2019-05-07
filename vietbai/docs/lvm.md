---
date: 2019-04-25
title: Logical Volume Manager (lvm) 
categories:
  - linux
description: Tìm hiểu và phân tích công nghệ lvm 
author: anhduc
tags: [linux,lvm]
type: Document
---

## Lời mở đầu 
Có lẽ ổ cứng là một thứ khá quen thuộc đối với một người dùng máy tính. Vậy dùng nó làm sao và trong linux có phương pháp nào sử dụng disk quản lý disk một cách tiện ích? thì ngày hôm nay tôi sẽ giới thiệu cho bạn biết về một công nghệ mà tôi tìm hiểu được đó chính là công nghệ Logical Volume Manager (lvm)
## Tổng quan về LVM Logical Volume Manager (lvm)
LVM là một phương pháp cho phép ấn định không gian đĩa cứng thành những Logical Volume khiến cho việc thay đổi kích thước trở nên dễ dàng ( so với partition ). LVM dùng để quản lý phần vùng disk trong linux

Với kỹ thuật Logical Volume Manager (LVM) bạn có thể thay đổi kích thước mà không cần phải sửa lại partition table của OS. Điều này thực sự hữu ích với những trường hợp bạn đã sử dụng hết phần bộ nhớ còn trống của partition và muốn mở rộng dung lượng của nó, bạn chỉ cần ấn định lại dung lượng mà không cần phân vùng lại, cũng không phải đối mặt với nguy cơ mất dữ liệu khi thay đổi dung lượng như khi thao tác trên Partition.


## 1. Một số thuật ngữ và lệnh cần thiết trong LVM 
- Physical volumes (PV): Là đĩa cứng vật lý trong server của bạn. Khi dùng LVM có thể kết hợp nhiều PV để tạo thành một Volume Groups với dung lượng bằng tổng dung lượng các PV. Tuy nhie6n PV chỉ là đại diện cho các ổ đĩa vật ký chứ không phải là bản thân ổ đĩa đó, vì vậy để cần phải tạo PV từ các dev đã mount.
-  Volume Groups (VG): là một tập hợp các PV, từ VG sẽ có thể phân chia thành các Logical Volumes và các Logical Volumes này có thể thay đổi kích thước dễ dàng.
 - Logical Volumes (LV): Là đơn vị cuối cùng của hệ thống LVM, các LV tương đương với partition theo cách phân chia truyền thống. LV có thể thay đổi kích thước dễ dàng, tất cả chỉ phụ thuộc vào kích thước của VG.
 - Fdisk : đây là lệnh dùng để phân vùng disk ra thành các vùng partition. các bạn có thể tìm hiểu về lệnh [tại đây](https://github.com/duckmak14/thuctapsinh/blob/master/Anhduc/liunux/docs/fdisk.md)
 - Muont: là một lệnh dùng để gắn một phân vùng vào cây thư mục `root`. Nếu ta không mount thiết bị lưu trữ vào thì ta không thể sử dụng được nó. Các bạn có thể hiểu rõ hơn về nó khi tìm hiểu về  [lệnh mount](https://github.com/duckmak14/thuctapsinh/blob/master/Anhduc/liunux/docs/mount.md)
