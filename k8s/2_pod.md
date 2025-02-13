## Pod

### Khái niệm  
Pod là đơn vị triển khai nhỏ nhất trong Kubernetes, đại diện cho một nhóm một hoặc nhiều container được quản lý chung, chia sẻ tài nguyên và chạy trên cùng một Worker Node.

### Đặc điểm
#### 1. Chạy một hoặc nhiều container
+ Thông thường, một Pod chứa một container chính (ví dụ: ứng dụng web).
+ Một Pod cũng có thể chứa nhiều container bổ trợ (ví dụ: logging sidecar, proxy).

#### 2. Chia sẻ tài nguyên
+ Các container trong Pod có thể chia sẻ mạng (Network Namespace) → dùng chung địa chỉ IP.
+ Có thể chia sẻ Storage Volume để lưu trữ dữ liệu chung.

#### 3. Vòng đời ngắn, không cố định
+ Pod không phải là một máy ảo, nó có thể bị xóa và tạo lại khi cần thiết.
+ Kubernetes sử dụng ReplicaSet hoặc Deployment để duy trì số lượng Pod mong muốn.
#### 4. Tạo pod
```
apiVersion: apps/v1
kind: Pod
metadata:
  name: my-app-pod
  labels:
    app: my-app
spec:
  containers:
    - name: my-app-container
      image: nginx
      ports:
        - containerPort: 8080
```

```
kubectl run pod-name --image=image-name 
```
