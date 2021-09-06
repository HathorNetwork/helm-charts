# Hathor Kubernetes Helm Charts


[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) 
![Release Charts](https://github.com/HathorNetwork/helm-charts/workflows/release-chart/badge.svg?branch=master)

## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

    helm repo add hathor-network https://<orgname>.github.io/helm-charts

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.

You can then run `helm search repo
hathor-network` to see the charts.


## Charts

### [Hathor FullNode](https://github.com/HathorNetwork/helm-charts/blob/main/charts/hathor-full-node)
- 0.1.x includes HathorCore v0.41.x

To install the chart:

    helm install my-hathor-fullnode hathor-network/hathor-fullnode

To uninstall the chart:

    helm delete my-hathor-fullnode

## License

<!-- Keep full URL links to repo files because this README syncs from main to gh-pages.  -->

[Apache 2.0 License](https://github.com/HathorNetwork/helm-charts/blob/main/LICENSE).
