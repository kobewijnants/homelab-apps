# homelab-apps

My homelab apps that get automaticly deployed to kubernetes using ArgoCD

## Bootstrap ArgoCD

```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

Apply root app to configure ArgoCD

```bash
kubectl apply -f bootstrap/root-app.yaml
```

Get the argoCD password for the admin user:

```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```