
#### create
```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: rs-test
  labels:
    app: app-eks
spec:
  # modify replicas according to your case
  replicas: 3
  selector:
    matchLabels:
      app: app-test
  template:
    metadata:
      labels:
        app: app-test
    spec:
      containers:
      - name: app-eks-v1
        image: vietaws/eks:v1
```
#### expose
```
kubectl expose rs rs-test --name=svc3 --type=NodePort --port=8080 
service/svc3 exposed
```
