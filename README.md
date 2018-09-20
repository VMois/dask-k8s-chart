# Helm Chart for setting up autoscaling Dask cluster on Kubernetes

Currently, under active development. **Not suitable for production use!**

## Description

The chart for simple and fast setup of autoscaling [Dask](https://github.com/dask/distributed) cluster on Kubernetes for scientific computations.

Work is based on:

- [Dask](https://dask.pydata.org/en/latest/) and [Dask distributed](https://distributed.readthedocs.io/en/latest/index.html) libraries
- [Dask Kubernetes](https://github.com/dask/dask-kubernetes) repo
- [Dask Helm Chart](https://github.com/dask/helm-chart/tree/master/dask)

Thank you!

## How it works

The chart will set up a Kubernetes deployment with a single pod called *scheduler* (based on this [Docker custom image](https://github.com/VMois/dask-k8s-docker/tree/master/scheduler)). The pod will have two ports exposed:

- **8786** for client connections (check [Dask docs](https://distributed.readthedocs.io/en/latest/client.html) for more info)
- **8787** for web dashboard

The scheduler pod will launch 1 *worker* pod (based on this [Docker custom image](https://github.com/VMois/dask-k8s-docker/tree/master/worker)) for performing computations. After connecting to the cluster, you will be able to run different tasks using Dask interface and more. During tasks execution, based on CPU and memory usage, a scheduler will automatically scale up (add more worker pods) or scale down (remove some worker pods).

## Use cases

Later...

## How to setup

- Clone the repo:

```bash
git clone https://github.com/VMois/dask-k8s-chart.git
```

- Install using helm:

```bash
helm install dask-k8s-chart/ --name RELEASE_NAME
```

A **scheduler** pod should have permissions to create other pods.

## Contributions

Any fixes, suggestions and improvements are welcome. Don't hesitate to open an issue)

Possible topics for contributions:

- extend setup and configure guide
