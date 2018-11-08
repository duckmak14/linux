# Tìm hiểu về vi và vim 

# 1.khái niệm

- Vi: 	- Vi là viết tắt của từ Video Interactif là chương trình sọan thảo văn bản theo trang màn hình

		- Vi có 3 chế độ hoạt động:

			- Command mode: Chế độ lệnh 
			
			- Insert mode: Chế độ soạn thảo văn bản để giúp ghi và chỉnh sửa văn bản
		
		- Một số thao tác lệnh tệp tin: 
		
			- Lệnh xóa:
				
				-  `x` hoặc phím delete: xao 1 ký tự
				
				-  `dd` xóa 1 dòng, tính từ vị trí con trỏ
				
				-  `2dd` xóa 2 dòng, muốn xóa nhiều dòng bạn thêm số bất kỳ vào.
				
				-  `dw` xóa 1 từ bên phải con trỏ
				
				-  `db` xóa từ bên trái con trỏ
				
			- Lệnh copy và paste:
			
				-  `yy` copy 1 dòng tại vị trí con trỏ

				-  `y1` copy 2 dòng, giá trị được tính từ 0, copy 3 dòng là y2, 4 dòng là y3

				-  `p` dán kết quả copy tại vị trí con trỏ.
				
			- Lệnh lưu và thoát
			
				-  `:w` lưu và không thoát VI

				-  `:w` newfile.txt lưu file đang làm việc sang một file mới, giống save as trong MSWord.

				-  `:wq` lưu và thoát VI

				-  `:q!` không lưu và thoát VI
				
			-  Tìm kiếm và thay thế

				-  /text1 tìm kiếm từ text1 từ trên xuống

				-  ?text1 tìm kiếm từ text1 từ dưới lên

				-  n để nhảy đến kết quả tìm kiếm tiếp theo

				-  :%s/text1/text2/g thay text1 bằng text2s
				
			-  
