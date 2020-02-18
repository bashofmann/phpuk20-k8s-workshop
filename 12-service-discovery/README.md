# Service Discovery

## Everyone

* Deploy quote-svc
```
kubectl apply -f quote-svc/deployment/
```

* Deploy hello-svc
```
kubectl apply -f hello-svc/deployment/
```

* Deploy web-application
```
kubectl apply -f web-application/deployment/
```

## Or create a helm chart for the new services

* Scaffold charts

```
mkdir helm-charts
cd helm-harts
helm create quote-svc
helm create hello-svc
```

* Adapt charts

* Install quote-svc
```
helm upgrade --install quote-svc helm-charts/quote-svc -f quote-svc-values.yaml
```

* Install hello-svc
```
helm upgrade --install hello-svc helm-charts/hello-svc -f hello-svc-values.yaml
```

* Print YAML that helm would apply

```
 helm template hello-svc helm-charts/hello-svc -f hello-svc-values.yaml -f hello-svc-stage.yaml --set image.tag=10.0.1
```

* Test installation
```
helm test hello-svc
```

* Install helm-kubeval plugin

```
helm plugin install https://github.com/instrumenta/helm-kubeval
```

* Validate chart against Kubernetes schema

```
helm kubeval helm-charts/hello-svc
```

* Install helm-diff plugin

```
helm plugin install https://github.com/databus23/helm-diff --version v2.11.0+5
```
* Change something in the hello-svc chart
* Run helm-diff

```
helm diff upgrade hello-svc helm-charts/hello-svc -f hello-svc-values.yaml -f hello-svc-stage.yaml
```

* Upgrade the chart

```
helm upgrade hello-svc helm-charts/hello-svc -f hello-svc-values.yaml -f hello-svc-stage.yaml
```
