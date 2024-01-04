# postgresql-in-kubernetes

these manifests can help install potsgresql on kubernetes

first you need create secret

```
kubectl create secret generic postgresql --from-literal POSTGRES_USER="youruser" --from-literal POSTGRES_PASSWORD="yourpassword" --from-literal POSTGRES_DB="defaultdb"
```

after that apply configmap, service and statefulsets

```
kubectl apply -f postgres-cm.yaml
kubectl apply -f postgres-svc.yaml
kubectl apply -f postgres-sts.yaml
```
