# Exercise

## Everyone

Use the docker image bashofmann/exercise-app:1.0.0

* Create a Deployment
* Create a Service of type ClusterIP (no external LoadBalancer)
* Create an Ingress Resource that routes traffic to this Service and uses TLS

Bonus:

* Create a ConfigMap with a USERNAME and inject it into the Deployment as an environment variable
