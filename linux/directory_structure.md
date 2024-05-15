## Các cấu trúc thư mục của file system chính

+ / : root directory( bố của các thư mục)
+ /var(variables): chứa các tập tin tăng dần kích thước theo thời gian(log files, lib, ...)
+ /home: chứa thư mục của người dùng
+ /opt(optional software): thư mục sử dụng cho các phần mềm của các bên thứ ba.

## Swap space

+ Khi một tỷ lệ của RAM bị đầy. Linux kernel sẽ chuyển data ít dùng hơn sang Swap
+ Có 2 loại :
  + Swap partition
  + Swap file
+ Nên để Swap dưới 50% dung lượng RAM

## Partitions and mount points

+ Một partition là một phân chia logic của một thiết bị lưu trữ vật lý như HDD, SSD
+ Mỗi phân vùng thường có một hệ thống tập tin riêng phục vụ cho các mục đích khác nhau

+ mount points : liên kết 1 thư mục vào 1 thư mục khác trong hệ thống( mount 1 ổ cứng mới vào 1 thư mục, mount 1 thư mục vào 1 thư mục)

## LVM(Logical volume manager)

+ Cho phép các nhóm ổ đĩa hoặc partitions có thể tập hợp thành 1 hoặc các file systems
  + Physical volume: là 1 ổ cứng hoặc partition
  + Volume group: là nhóm các physical volume
  + Logical volume: là các partition của volume group