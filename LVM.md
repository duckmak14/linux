# 1.Khái niệm 
a) LVM
-LVM: là phươn pháp ấn định không gian đĩa cứng thành những logical volume khiến cho việc thay đổi kích thước trở lên dễ  dàng hơn. Khi dùng LVM giúp ta có thể thay đổi khích thước mà không cần phải sửa table của OS.
- Physical volume: là một đĩa cứng vật lý hoặc là partition 
- Volume group: là một nhóm các physical volume ( ổ đĩa ảo )
- logical volume: là các phân vùng ảo của ổ đĩa ảo 
b) Những khái niệm liên quan 
- Ổ cứng (HDD): là thiết bị lưu trữ của máy tính. Nó là loại bộ nhớ không thay đổi và không bị mất dữ liệu khi ta ngừng cung cấp nguồn điện cho chúng 
- Partition: là các phân vùng của ổ cứng. Mỗi một ổ cứng có 4 partition. Trong đó bao gồm 2 loại là primary partition và extended partition 
    - primary partition: còn được gọi là phân vùng chính, có thể khởi động và mỗi ổ cứng chỉ có tối đa 4 phân vùng này 
    - extended partition: Hay còn được gọi là phân vùng mở rộng của ổ cứng
c) Vậy phân vùng có tác dụng gì? tại  sao phải phân vùng ổ cứng? 
- Sự phân chia ổ cứng có thể định dạng các loại tệp tin khác nhau để có thể cài đặt được nhiều hệ điều hành đồng thời trên cùng một ổ cứng.
- Phân chia ổ cứng không phải là một sự bắt buộc đối với một đĩa cứng 
- Phan vùng giúp cho việc quản lý các nội dung lưu trữ và phân loại dữ liệu được tốt hơn 
- Phân vùng gồm:
    - Phân vùng chính(primary): tối đa có 4 phân vùng chính 
    - Phân vùng Extended : là nơi có thể chia ra thành các phân vùng logical 
    - Phân vùng logical: Là loại phân vùng bé nhất nằm trong các phân vùng lớn hơn
- Một vài định dạng File System trong linux
    - Một ổ cứng mới sau khi phân vùng cần phải được định dạng 
    - Ext: là định dạng file system đầu tiên được thiết kế dành cho linux có tất cả gồm 4 phiên bản từ Ext1 đến Ext4. Hiện nay đa phần người dùng Ext4 vì nó có thể giảm bớt  hiện tượng phân mảnh dữ liệu trong ổ cứng, hỗ trợ các file và phân vùng có dung lượng lớn...
    - XFS: Nó khá giống với Ext4 về mốt số mặt. như hạn chế phân vùng dữ liệu, không cho phép các snapshot tự động kết hơp với nhau, hỗ trợ nhiều file dung lượng lớn...
    - JFS: Điểm mạnh của JFS là tiêu tốn tài nguyên hệ thống và đạt hiệu suất hoạt động tốt hơn, tốc độ kiểm tra ổ đĩa nhanh hơn so với các phiên bản Ext 
d) Quản lý phân vùng trong linux
- Qui tắc đặt tên đĩa
    - IDE hard disks:
        - `dev/hda` : Primary master IDE (often the hard disk)
        - `/dev/hdb`: Primary slave IDE
        - `/dev/hdc`: Secondary master IDE (often a CD-ROM)
        - `/dev/hdd`: Secondary slave IDE
    - SCSI device files
        - `/dev/sda`: First SCSI drive
        - `/dev/sdb`: Second SCSI drive
        - `/dev/sdc`:Third SCSI drive (and so on)
- Qui tắc đặt tên partition
    - Primary partitions
        - /dev/hda1
        - /dev/hda2
        - /dev/hda3
        - /dev/hda4
- Extended partitions
    - /dev/hda1 (primary)
    - /dev/hda2 (extended)
- Logical partitions
    - /dev/hda1 (primary)
    - /dev/hda2 (extended)
    - /dev/hda5 (logical)
    - /dev/hda6 (logical)
    - /dev/hda7 (logical)
    - /dev/hda8 (logical)
- Quản lý phân vùng trên linux
    - Lệnh liệt kê các phân vùng `fdisk -l` hoặc `lsblk`
    *thiếu ảnh*
    - Nếu muốn tạo ra một phân vùng trên ổ cứng thì ta dùng lệnh fdisk để vào 
        - ví dụ: `fdisk /dev/sda` 
        *thiếu ảnh*
        - sau khi vào xong ấn m để hiển thị những trợ giúp 
        *thiếu ảnh*
        - Một vài nút cơ bản 
            - `n`: tạo mới 
                - Như ta nhìn thấy ở đây có 1 phân vùng primary 0 phân vùng extended 
                - chọn p để tạo ra một phân vùng primary và e để tạo extended
                - chọn số phân vùng mặc định ở đây là 2 bạn có thể chọn từ 2 tới 4
                - Cuối cùng, xác định sector cuối của phân vùng. Ấn Enter để chấp nhật sử dụng hết phần ổ đĩa còn trống. Thay vì chỉ định sector, bạn có thể chỉ định kích thước, chữ viết tắt tương ứng: K – Kilobyte, M – Megabyte và G – Gigabyte. Ví dụ, gõ “+5G” cho phân vùng với kích thước 5 Gigabyte. Nếu bạn không gõ đơn vị sau dấu “+”, fdisk sẽ lựa chọn sector làm đơn vị. Ví dụ, nếu bạn gõ “+10000”, fdisk sẽ cộng thêm 10000 sector để làm điểm kết thúc của phân vùng.
                - chọn `q` để lưu và thoát
            - `d`: xóa
            - `e`: để thêm một phân vùng extended
        * Note: Mỗi máy chỉ có tối đa 4 phân vùng primary