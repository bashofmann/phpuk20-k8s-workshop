# Monitoring

## Presenter only

Install prometheus

```
kubectl create namespace monitoring
kubectl apply -f basic-auth.yaml
helm upgrade --install --namespace monitoring -f values.yaml prom stable/prometheus-operator
kubectl apply -f dashboards/
kubectl apply -f service-monitors/
```

Install blackbox-exporter

```
kubectl apply -f blackbox-exporter/
```

## Everyone

Install ServiceMonitor for blackbox-exporter targeting web-application


```
kubectl apply -f blackbox-exporter-service-monitor/
```
