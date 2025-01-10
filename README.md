# Milim

Talos powered Kubernetes cluster.

Currently includes :
- 3 control panes
- 2 worker nodes

If you want more see [here](https://github.com/Samoth69/IAC/tree/master/Infra/terraform)

## usefull commands

```bash
# force update flux
flux reconcile source git home-kubernetes
# get flux objects status
flux get all -A --status-selector ready=false
# token for the dashboard
kubectl -n kubernetes-dashboard create token admin-user
# to connect to primary database
while true; do kubectl -n database port-forward "$(kubectl -n database get pods -l postgres-operator.crunchydata.com/role=master -o name)" 5432:5432; done
# hubble
cilium hubble port-forward&
hubble observe --verdict DROPPED -f
```
