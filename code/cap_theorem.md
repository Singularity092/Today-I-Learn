## CAP
### Consistency
 - Đảm bảo dữ liệu nhất quán  
 - Ví dụ: Cập nhật giá trị ở db 1 thành 2, khi lấy ra thì đc giá trị 2
### Availability
 - Nhận request -> xử lý -> phản hồi cao nhất
### Partition Tolerance  
 - Vấn đề về mạng, các node k giao tiếp được với nhau, xử lý độc lập gây mất đồng bộ k nhất quán với nhau.