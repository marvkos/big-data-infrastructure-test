# ArgoCD Demo Project
This project will test ArgoCD in a minicube environment.

## Resources
https://minikube.sigs.k8s.io/docs/start/

https://argo-cd.readthedocs.io/en/stable/getting_started/

## Commands
```
minikube start
minikube dashboard
minikube stop
minikube delete

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/core-install.yaml

kubectl port-forward svc/argocd-server -n argocd 8080:443
```
