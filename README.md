# postgresql-in-kubernetes

these manifests can help install potsgresql on kubernetes

first you need create secret

```
kubectl create secret generic postgresql --from-literal POSTGRES_USER="youruser" --from-literal POSTGRES_PASSWORD="yourpassword" --from-literal POSTGRES_DB="defaultdb"
```

after that apply configmap, service and statefulsets. just you need change storageclass in sts yaml. if you use EKS AKS cloud managed kubernetes you need type right storageclass name if you use local kubernetes you can use "standard"

```
kubectl apply -f postgres-cm.yaml
kubectl apply -f postgres-svc.yaml
kubectl apply -f postgres-sts.yaml
```
