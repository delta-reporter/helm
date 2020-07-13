# Delta Reporter Helm Repository
Helm chart for Kubernetes deployments

To deploy Delta Reporter into Minikube, follow this instructions:

1. First add this repo to Helm and install Delta Reporter

```
helm repo add delta https://delta-reporter.github.io/helm
helm install delta-reporter delta/delta-reporter
```

#### If no errors are met, Delta Reporter should be alive into Minikube, so we just need to expose it

2. Expose Delta Reporter's Core service

```
kubectl delete service delta-core
kubectl expose deployment delta-core --type=LoadBalancer
minikube service delta-core --url
```
3. Expose Delta Reporter's Frontend service

```
kubectl delete service delta-frontend
kubectl expose deployment delta-frontend --type=LoadBalancer
minikube service delta-frontend --url
```
