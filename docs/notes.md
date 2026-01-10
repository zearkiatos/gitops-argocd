# Install ArgoCD

## Install pods
```sh
$ kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
## Forward port
```sh
$ kubectl port-forward svc/argocd-server -n argocd 8080:443
```

## Get password
```sh
$ kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

```