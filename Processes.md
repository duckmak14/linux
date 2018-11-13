# I.Khái niệm 
## 1.khái niệm
- Processes( tiến trình ): là một chương trình đang xử lý 
- Một tiến trình có thể cần đến một số tài nguyên của máy: CPU, bộ nhớ chính, các tệp tin...
- Chương trình: là nơi chứa đựng các chỉ thị điều khiển máy tính. khi các chỉ thị này được thực hiện thì chương trình chuyển thành tiến trình.
- Một tiến trình được coi là một đơn vị làm việc của hệ thống 
- Các tiến trình có thể đọc lập với nhau hoặc không thể độc lập với nhau 
- Hệ điều hành sẽ phân bố tài nguyên của máy tính cho các tiến trình 
- Khi một máy tính chạy thì thường sẽ luôn có rất nhiều chương trình chạy song song chúng ta cứ tưởng rằng trong một thời điểm máy tính sẽ thực hiện nhiều chương trình nhưng trong thực tế các chương trình được chạy tuần tự với nhau đây gọi là sự hoạt động theo cơ chế đa nhiệm 
- Theo nhiệm vụ đang được thực hiện thì có thể có nhiều quy trình khác nhau
## 2. Cách thức hoạt động và phân loại 
- Tiến trình ở trạng thái hoạt động: là nó đang ở trong trạng thái thực thi các lệnh ở trong CPU 
-  Tại bất cứ thời điểm nào thì cũng có rất nhiều tiến trình đang hoạt động. Nên để kiểm soát được tiến trình thì hệ điều hành gán cho chúng một ID để dễ dàng quản lý các tiến trình 
- Theo ta biết thì tại một thời điểm CPU chỉ có thể xử lý được một tiến trình nên khi có rất nhiều tiến trình thì sẽ có sự chậm trễ và CPU làm việc theo sự ưu tiên của các quy trình được linux chỉ định 
- Mỗi một tiến trình cần bao nhiêu thời gian và bao nhiêu thời gian đã được cấp cho một tiến trình tất cả các quá trình trong trạng thái này được nằm trên một hàng đợi chạy.
- Có những tiến trình để có thể tiếp tục chạy thì cần đến một thao tác tổ hợp phím hay một lệnh nào đó từ người sử dụng. Nó Không thực sự đang chạy như một tiến trình nhưng mà nó vẫn xuất hiện trong danh sách quy trình của hệ thống 