- Tác dụng:  
    + cho phép cách ly và ảo hóa các tài nguyên hệ thông như mạng, quyền truy cập tệp ...
    + cho phép tạo môi trường ảo cách ly hoàn toàn với môi trường chính (triển khai container trong docker)
- Ví dụ:  
    - Cài đặt 2 version database trên linux  
        + Vấn đề:   
            - 2 version đều cài đặt ở cùng thư mục(ubuntu thường duy trì một phiên bản của thư viện)
            - 2 db truy cập chung port 
        + Giải quyết  
            - Namespace mount: bind thư mục trong namespace vào file system, khi đó thư mục của 2 version database cùng trỏ vào file system, giúp 2 version biệt lập hoàn toàn.  

            >**mkdir /root/sql-dependencies-v1**  
             **mkdir /root/sql-dependencies-v2**

            >**unshare --mount=/tmp/dbv1 -- /bin/bash**  
             **mount -o bind /root/sql-dependencies /root/sql-dependencies-v1**  
             **exit**

            >**unshare --mount=/tmp/dbv2 -- /bin/bash**  
             **mount -o bind /root/sql-dependencies /root/sql-dependencies-v2**  
             **exit**
            
            Giúp 2 db sử dụng thư viện và tài nguyên từ /root/sql-dependencies
            - Namespace network : 