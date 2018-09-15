# Helm Chart for setting up dynamic Dask cluster on Kubernetes
Currently, under active development. **Not suitable for production use!**

## Description
Chart is based on two Docker images:
- [vmois/dask-k8s-scheduler](https://github.com/VMois/dask-k8s-docker)
- [vmois/dask-k8s-worker](https://github.com/VMois/dask-k8s-docker)

## How to setup?
1. Clone the repo:
```bash
git clone https://github.com/VMois/dask-k8s-chart.git
```

2. Install using helm:
```
helm install dask-k8s-chart/ --name RELEASE_NAME
```
