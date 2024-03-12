Bảng chức năng điều khiển cảm biến góc:
Ký tự	  Chức năng
A, a	  Reset góc hiện tại về 0
F, f	  Lấy mẫu góc
X	      Chế độ chỉ gửi giá trị trục X khi truyền
x	      Chế độ tự động gửi giá trị trục X
Y	      Chế độ chỉ gửi giá trị trục Y khi truyền
y	      Chế độ tự động gửi giá trị trục Y
Z	      Chế độ chỉ gửi giá trị trục Z khi truyền
z	      Chế độ tự động gửi giá trị trục Z

Frame cảm biến góc gửi về VĐK:
Trục |	Header	|          Angle        |
  x	 |   x	    |                       |
  y	 |   y			|  A1	  |    A2	  |  A3 |
  z	 |   z			|                       |
Note: Truyền ký tự in hoa -> giá trị Header nhận về cũng là in hoa và ngược lại với ký tự thường.
Khôi phục giá trị góc:
Angle = (A1 * 10000 + A2 * 100 + A3) – 500000
