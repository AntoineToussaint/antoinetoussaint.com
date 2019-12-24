# Antoine's blog

These are the steps to install/maintain a blog with `ghost` in Kubernetes.

## Setup

```sh
helm install blog -f helm/config.yaml \
    --namespace blog \
    --set ghostPassword=${GHOST_PASSWORD} \
    --set mariadb.mariadbRootPassword=${GHOST_MARIADB_PASSWORD} \
    stable/ghost
```

**Note:** You may need to add the `stable` Chart repository with:

```sh
helm repo add stable https://kubernetes-charts.storage.googleapis.com/
```
