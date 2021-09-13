# Hathor FullNode

This is a Helm Chart that deploys a hathor-core instance (fullnode) for the [Hathor Network](https://hathor.network/) blockchain.

The hathor-core source code can be found in https://github.com/HathorNetwork/hathor-core

## TL;DR

```bash
$ helm repo add hathor-network https://hathornetwork.github.io/helm-charts
$ helm install my-hathor-fullnode hathor-network/hathor-fullnode
```

## Introduction

This chart bootstraps a hathor-core Statefulset.

An initContainer will generate a peer-id on its first run, save it to the persistent volume, and reuse it in case the fullnode is restarted. Uninstalling the chart will also remove the persistent volume, consequently removing the peer-id file.

Another initContainer downloads a database snapshot for the network in use (mainnet or testnet), if it detects the database is missing. It will not do so in subsequent runs, unless the database went missing for any reason.


## Prerequisites
- Kubernetes
- Helm 3
- PV provisioner support in the underlying infrastructure


## Paramenters

### Hathor parameters
| Name                              | Description                                                                    | Value           |
| --------------------------------- | ------------------------------------------------------------------------------ | --------------- |
| `hathor.network`                  | Selects to which network the fullnode will connect (mainnet or testnet)        | `testnet`       |
| `hathor.cliOptions.cache.enabled` | Enabled the cache of transactions in the fullnode                              | `true`          |
| `hathor.cliOptions.cache.size`    | Sets how many transactions to keep cached                                      | `100000`        |
| `hathor.cliOptions.xFastInitBeta` | Executes a fast initialization, which skips some transaction verifications     | `true`          |
| `hathor.cliOptions.walletIndex`   | Create an index of transactions by address and allow searching queries         | `true`          |

### Common parameters

| Name                     | Description                                                                             | Value           |
| ------------------------ | --------------------------------------------------------------------------------------- | --------------- |
| `nameOverride`           | String to partially override common.names.fullname                                      | `""`            |
| `fullnameOverride`       | String to fully override common.names.fullname                                          | `""`            |

### Statefulset parameters
| Name                             | Description                                                                       | Value         |
| -------------------------------- | --------------------------------------------------------------------------------- | ------------- |
| `statefulset.replicas`           | Sets the number of replicas in the statefulset                                    | `hathornetwork/hathor-core` |
| `image.repository`               | Repository where the image is located                                             | `1`           |
| `image.pullPolicy`               | Image pull policy                                                                 | `IfNotPresent` |
| `image.tag`                      | Image tag. It uses the chart appVersion by default if empty                       | `""`          |
| `imagePullSecrets`               | imagePullSecrets used in Statefulset spec                                         | `[]`          |
| `envFrom`                        | Used to provide additional environments variables to the container                | `{}`          |
| `resources`                      | Resources definition                                                              | `{}`          |
| `nodeSelector`                   | Node selector                                                                     | `{}`          |
| `tolerations`                    | Tolerations                                                                       | `{}`          |
| `affinity`                       | Affinity                                                                          | `{}`          |
| `serviceAccount.create`          | Specifies whether a service account should be created                             | `true`        |
| `serviceAccount.name`            | Service account name                                                              | `""`          |
| `serviceAccount.annotations`     | Service account annotations                                                       | `{}`          |
| `podAnnotations`                 | Pod annotations                                                                   | `{}`          |
| `podSecurityContext`             | Pod security context                                                              | `{}`          |
| `securityContext`                | Security context                                                                  | `{}`          |
| `persistentVolumeClaim.storageClassName`           | The storage class to use for persistent volumes                 | `gp2`         |
| `persistentVolumeClaim.resources.requests.storage` | The storage to allocate to the persistent volume                | `30Gi`        |

### Ingress parameters
| Name                             | Description                                                                       | Value         |
| -------------------------------- | --------------------------------------------------------------------------------- | ------------- |
| `ingress.enabled`                | Enables/disables ingress                                                          | `false`       |
| `ingress.className`              | Ingress class name                                                                | `""`          | 
| `ingress.annotations`            | Ingress annotations                                                               | `{}`          | 
| `ingress.hosts`                  | Ingress host definitions                                                          | `[]`          | 
| `ingress.tls`                    | Ingress tls definition                                                            | `[]`          | 