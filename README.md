# Let's Learn Argo

Docker images at https://hub.docker.com/repository/docker/ajbot/containers-for-testing/general

Starting here: https://youtu.be/MeU5_k9ssrs?t=1565

Using k3d instead of minikube 

1 - Install ArgoCD in k8s 
2 - Configure ArgoCD with "application" CRD
3 - Test setup with deployment.yaml updates 

# 1 
```
kubectl create ns argocd 
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

Port forward
```
k port-forward -n argocd svc/argocd-server 8080:443
```

Pull admin secret from k8s 
```
k get secret argocd-initial-admin-secret -n argocd -o yaml
```