//TODO: 
## Tác dụng

 - Đóng gói, phân phối, triển khai application

## Thành phần
- docker client: nhận lệnh từ người dùng
- docker host: xử lý lệnh, quản lý docker object và kết nối với docker registry
- docker registry: quản lý và phân phối docker image

## Cấu trúc lệnh
```
docker <object> <command> <option>
```

## ...
- Docker image  là file template tạo ra container, gồm file binary và dependencies
- Container là môi trường ảo hóa độc lập, hoàn chỉnh: chứa chương trình và các gói bổ sung.
- Docker image là các read only layer xếp chồng lên nhau

- Dùng docker save và docker load để phân phối và thêm image docker.