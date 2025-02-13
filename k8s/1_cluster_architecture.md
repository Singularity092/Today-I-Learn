# Kubernetes - Kiến trúc Cluster

## Kiến trúc
![image](../image/kubernetes-cluster-architecture.svg)
## Master Node
Master Node chịu trách nhiệm điều phối và quản lý toàn bộ cluster trong Kubernetes. Nó bao gồm các thành phần chính:

1. **API Server**
   - Cung cấp giao diện RESTful API để tương tác với cluster.
   - Là trung tâm giao tiếp giữa các thành phần trong Kubernetes.
   
2. **Scheduler**
   - Xác định Node phù hợp để chạy Pod dựa trên tài nguyên khả dụng và ràng buộc (constraints).
   - Theo dõi các Pod chưa được gán vào Node và thực hiện việc lên lịch (scheduling).

3. **ETCD**
   - Lưu trữ toàn bộ dữ liệu cấu hình của cluster dưới dạng key-value.
   - Đảm bảo tính nhất quán và khả dụng của dữ liệu trong hệ thống phân tán.

4. **Controller Manager**
   - Chạy các controller như Node Controller, Replication Controller, Endpoint Controller,...
   - Giám sát trạng thái cluster và thực hiện các hành động cần thiết để đảm bảo trạng thái mong muốn.

## Worker Node
Worker Node chịu trách nhiệm chạy các ứng dụng (Pods) trong Kubernetes. Thành phần chính của Worker Node bao gồm:

1. **Kubelet**
   - Là thành phần chính của Worker Node, chịu trách nhiệm giao tiếp với API Server.
   - Kiểm soát vòng đời của container trong Pod.
   - Giám sát tình trạng của Pod và đảm bảo Pod đang chạy đúng theo yêu cầu.

2. **Kube Proxy**
   - Duy trì các quy tắc mạng để cho phép giao tiếp giữa các Pods và Services.
   - Định tuyến lưu lượng mạng trong cluster.

3. **Container Runtime**
   - Chạy các container của ứng dụng, có thể sử dụng Docker, containerd hoặc CRI-O.

## Kiến trúc Cluster
- **Control Plane** (Master Node): Quản lý và điều phối cluster.
- **Data Plane** (Worker Node): Chạy các ứng dụng và xử lý workload.

