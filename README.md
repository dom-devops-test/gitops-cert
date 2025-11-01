# gitops-cert

# Kind Cluster

* Create Kind Cluster:

```
kind create cluster --config ./kind-config/cluster.yaml
```

* Usefull Kind Commands

```
kind get clusters
```

* Delete Kind Cluster:

```
kind delete cluster --name my-cluster
```

## Environment Setup

### Install argocd

```
kubectl create ns argocd
helm install argocd argo/argo-cd --version 6.10.2 -n argocd
# Once installed get password with 
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```