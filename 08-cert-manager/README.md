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

* Add AWS API Tokes to `route53/credentials-secret.yaml` and `route53/clusterissuer.yaml`

* Create ClusterIssuer
```
kubectl apply -f route53/credewntials-secret.yaml
kubectl apply -f route53/clusterissuer.yaml
```

* Create wildcard certificate
```
kubectl apply -f route53/certificate.yaml
```
