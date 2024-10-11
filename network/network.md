# IP Addressing and Subnetting

## 1.Các loại địa chỉ  trong mạng máy tính

### 1.1 MAC Address (Địa chỉ Media Access Control)
+ Là một định danh vật lý, được gán cố định cho card mạng, lưu trữ trong phần cứng của thiết bị, có thể thay đổi địa chỉ MAC thông qua phần mềm.
+ Hoạt động ở tầng vật lý (physical layer).
+ Mỗi thiết bị có một địa chỉ MAC duy nhất, không thể trùng lặp trong cùng một mạng. Nếu thay đổi địa chỉ MAC dẫn đến trùng lặp thì sẽ xung đột dữ liêu, mất mạng.
+ Switch layer 2 dùng địa chỉ MAC để xác định thiết bị trong mạng để gửi gói tin
+ Router sẽ nhận dạng thiết bị bằng địa chỉ MAC và có thể cấu hình để chỉ cho phép những địa chỉ MAC nhất định truy cập mạng.
### 1.2 Địa chỉ IP (Internet Protocol)
+ Là một định danh logic trên lớp mạng, dùng để xác định duy nhất một thiết bị hoặc host trong một mạng nhất định
+ Có 2 phiên bản chính của địa chỉ IP:
    + IPv4
        + IPv4 là phiên bản đầu tiên và phổ biến nhất. Địa chỉ IPv4 được biểu diễn dưới dạng 4 số nguyên cách nhau bởi dấu chấm, với mỗi số có giá trị từ 0 đến 255. (192.168.0.1)
        + IPv4 chỉ cung cấp khoảng 4 tỷ địa chỉ (2^32), dẫn đến tình trạng hiện nay có thể thiếu hụt địa chỉ
    + IPv6
        + IPv6 được phát triển để khắc phục tình trạng thiếu địa chỉ của IPv4. Địa chỉ IPv6 được biểu diễn dưới dạng 8 nhóm số thập lục phân, mỗi nhóm có 4 ký tự, cách nhau bởi dấu hai chấm. (2001:0db8:85a3:0000:0000:8a2e:0370:7334)
        + IPv6 cung cấp 3.4 x 10^38 địa chỉ
+ Phân loại:
    + IP public: Là địa chỉ duy nhất trên internet, có thể truy cập từ mọi nơi,được gán cho các thiết bị server web, router,...
    + IP private: Là địa chỉ không thể truy cập trực tiếp từ internet, thường sử dụng trong nội bộ. Nằm trong các dải sau:
        + 10.0.0.0 đến 10.255.255.255
        + 172.16.0.0 đến 172.31.255.255
        + 192.168.0.0 đến 192.168.255.255

    + Dynamic IP: Là địa chỉ IP được cấp tự động từ máy chủ DHCP (Dynamic Host Configuration Protocol). Địa chỉ này có thể thay đổi mỗi khi thiết bị kết nối lại với mạng.
    + Static IP: Là địa chỉ IP được gán cố định cho một thiết bị trong mạng. Địa chỉ này không thay đổi trừ khi được cấu hình lại.