# Hathor Kubernetes Helm Charts


[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) 
[![Release Charts](https://github.com/HathorNetwork/helm-charts/actions/workflows/release-chart.yml/badge.svg)](https://github.com/HathorNetwork/helm-charts/actions/workflows/release-chart.yml)

## TL;DR

```bash
$ helm repo add hathor-network https://hathornetwork.github.io/helm-charts
$ helm search repo hathor-network
$ helm install my-release hathor-network/<chart>
```

## Before you begin

### Prerequisites
- Kubernetes 1.20+ (It's very likely that it will work on older versions, we just didn't tested yet)
- Helm 3

### Setup a Kubernetes Cluster

You will need a Kubernetes Cluster to run the Helm Charts. If you never worked with Kubernetes before, propably a good starting point would be to setup a local test cluster by checking [their guide](https://kubernetes.io/docs/tasks/tools/).

This way you will be able to test our Helm Chart.

### Install Helm

Helm is a tool for managing Kubernetes charts. Charts are packages of pre-configured Kubernetes resources.

To install Helm, refer to the [Helm install guide](https://github.com/helm/helm#install) and ensure that the `helm` binary is in the `PATH` of your shell.

### Add Repo

The following command allows you to download and install all the charts from this repository:

```bash
$ helm repo add hathor-network https://hathornetwork.github.io/helm-charts
```

### Using Helm

Once you have installed the Helm client, you can deploy a Bitnami Helm Chart into a Kubernetes cluster.

Please refer to the [Quick Start guide](https://helm.sh/docs/intro/quickstart/) if you wish to get running in just a few commands, otherwise the [Using Helm Guide](https://helm.sh/docs/intro/using_helm/) provides detailed instructions on how to use the Helm client to manage packages on your Kubernetes cluster.

Useful Helm Client Commands:
* View available charts: `helm search repo hathor-network`
* Install a chart: `helm install my-release hathor-network/<package-name>`
* Upgrade your application: `helm upgrade`

## Charts

All charts and detailed instructions about them can be found in their respective folders in https://github.com/HathorNetwork/helm-charts/blob/main/charts
## License

<!-- Keep full URL links to repo files because this README syncs from main to gh-pages.  -->

[Apache 2.0 License](https://github.com/HathorNetwork/helm-charts/blob/main/LICENSE).
