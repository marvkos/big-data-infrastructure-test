# ArgoCD Demo Project
This project will test ArgoCD in a minicube environment.

## Resources
https://minikube.sigs.k8s.io/docs/start/

https://argo-cd.readthedocs.io/en/stable/getting_started/
https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/

https://kubernetes.io/docs/concepts/workloads/controllers/deployment/

https://artifacthub.io/packages/helm/bitnami/spark

https://artifacthub.io/packages/helm/bitnami/kafka

## Commands
```
minikube start
minikube dashboard
minikube stop
minikube delete

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'
kubectl port-forward svc/argocd-server -n argocd 8080:443
minikube service -n argocd argocd-server

kubectl apply -n argocd -f apps/nginx-app.yaml
minikube service -n nginx nginx-service

kubectl apply -n argocd -f apps/spark-app.yaml
minikube service -n spark spark-master-svc

kubectl apply -n argocd -f apps/kafka-app.yaml
minikube service -n kafka kafka
```
## Ingress
```
minikube addons enable ingress
```
