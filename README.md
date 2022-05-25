# minikube-olm-argocd

Spins up a local Minikube cluster with OLM (Operator Lifecycle Manager) and ArgoCD Operator via OLM.

## Requirements:
 * `vendir`
 * `minikube`
 * `kubectl`

## Order of Operations

- `make mk-init` to initialize the MiniKube cluster and vendir in things.
- `make install`

## Notes

* Get Initial ArgoCD Password: `init_pwd=$(kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d) && echo $init_pwd`
* Forward port to ArgoCD-Server services: `k port-forward -n argocd svc/argocd-server 8080:443`
