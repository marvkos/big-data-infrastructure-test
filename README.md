# ArgoCD Demo Project
This project will test ArgoCD in a minicube environment.

## Resources
https://minikube.sigs.k8s.io/docs/start/

https://argo-cd.readthedocs.io/en/stable/getting_started/
https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/

https://kubernetes.io/docs/concepts/workloads/controllers/deployment/

## Commands
```
minikube start
minikube dashboard
minikube stop
minikube delete

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/core-install.yaml

kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'
kubectl port-forward svc/argocd-server -n argocd 8080:443

kubectl apply -n argocd -f application.yaml
```
