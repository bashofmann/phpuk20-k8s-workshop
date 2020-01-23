# 7. cert-manager

## Presenter only

* Install and configure cert-manager
```
kubectl apply --validate=false -f https://raw.githubusercontent.com/jetstack/cert-manager/release-0.12/deploy/manifests/00-crds.yaml
```

```
helm repo add jetstack https://charts.jetstack.io
```

```
helm repo update
```

```
kubectl create namespace cert-manager
```

```
helm upgrade --install --namespace cert-manager --version v0.12.0 cert-manager jetstack/cert-manager
```

* Add Digital Ocean API Token to `digitalocean/dns-secret.yaml`

* Create ClusterIssuer
```
kubectl apply -f digitalocean/dns-secret.yaml
kubectl apply -f digitalocean/clusterissuer.yaml
```

* Create wildcard certificate
```
kubectl apply -f digitalocean/certificate.yaml
```
