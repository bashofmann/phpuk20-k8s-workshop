# 9. Nginx Ingress Controller

## Presenter only

```
kubectl create namespace nginx-ingress
```
```
helm upgrade --install -f values.yaml --namespace nginx-ingress nginx-ingress stable/nginx-ingress
```

* Create wildcard DNS entry pointing to ingress controller external IP
