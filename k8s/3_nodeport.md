## NodePort

### Khái niệm
là một loại service cho phép truy cập ứng dụng từ bên ngoài cluster bằng cách mở  một cổng trên Node (port 30000-32767)

```yaml
apiVersion: apps/v1
kind: Service
metadata:
  name: nodeport-service
spec:
  type: NodePort
  selector:
    app: my-app
  ports:
    - protocol: TCP
      port: 80           # Cổng trong cluster (ClusterIP)
      targetPort: 8080   # Cổng mà Pod đang lắng nghe
      nodePort: 30007    # Cổng mở trên Node (tùy chọn)
```
+ end-user gửi request đến ip:port 30007
+ k8s service(type NodePort) chuyển request vào port 80(clusterIP port)
+ request chuyển tiếp đến port 8080

Ngoài cluster gọi đến port 30007
Trong cluster gọi đến port 80

```
kubectl expose pod pod-name --type=NodePort --port=8080 --target-port=8080 --name=nodeport-name

- get port
kubectl get svc nodeport-name

- get ip 
kubectl get nodes -o wide
```
