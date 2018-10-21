# Helm Chart for setting up auto-scaling Dask cluster on Kubernetes

Currently, under active development. **Not suitable for production use!**

## Description

The Helm chart for simple and fast setup of auto-scaling [Dask](https://github.com/dask/distributed) cluster on Kubernetes for scientific computations.

This project is created with help of:

- [Dask](https://dask.pydata.org/en/latest/) and [Dask distributed](https://distributed.readthedocs.io/en/latest/index.html)
- [Dask Kubernetes](https://github.com/dask/dask-kubernetes) repo
- [Dask Helm Chart](https://github.com/dask/helm-chart/tree/master/dask)

## How it works

The chart will set up a Kubernetes deployment with a single pod called *scheduler* (based on this [Docker custom image](https://github.com/VMois/dask-k8s-docker/tree/master/scheduler)). The pod will have two ports exposed:

- **8786** for client connections (check [Dask docs](https://distributed.readthedocs.io/en/latest/client.html) for more info)
- **8787** for web dashboard

By default, the scheduler pod will launch 1 *worker* pod (based on this [Docker custom image](https://github.com/VMois/dask-k8s-docker/tree/master/worker)). 
After connecting to the cluster, you will be able to run different tasks using Dask interface. 
The scheduler will automatically scale worker pods according to CPU and memory usage.

## Use cases

Later...

## How to setup

1. Install Helm on your Kubernetes cluster

2. Clone the repo:

```bash
git clone https://github.com/VMois/dask-k8s-chart.git
```

3. Install chart:

```bash
helm install dask-k8s-chart/ --name RELEASE_NAME
```

## Contributions

Any fixes, suggestions and improvements are welcome. 
Don't hesitate to open an issue, your help is very important)

Possible ideas for contributions:

- write detailed configuration tutorial
- test cluster stability

Thank you!
