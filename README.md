# s3proxy

![Version: 1.3.1](https://img.shields.io/badge/Version-1.3.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: v2.1.1_1.1.2](https://img.shields.io/badge/AppVersion-v2.1.1_1.1.2-informational?style=flat-square)

[![Main CI](https://github.com/s3proxy-distro/helm-s3proxy/actions/workflows/ci-main.yml/badge.svg)](https://github.com/s3proxy-distro/helm-s3proxy/actions/workflows/ci-main.yml)

Deployment for s3proxy based on the s3proxy-distro fork (from this org). This helm chart helps quickly and correctly
deploy and confidently by adding integration testing through ci.

## Install

## Using OCI registry

```bash
helm login ghcr.io
helm pull oci://ghcr.io/s3proxy-distro/charts/s3proxy --version ^1.0.0
```

## Using Chart Repo

```bash
helm repo add s3proxy https://s3proxy-distro.github.io/helm-s3proxy
helm upgrade --install releasname -f values s3proxy/s3proxy
```

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| ryanfaircloth |  |  |

## Source Code

* <https://github.com/s3proxy-distro/s3proxy>
* <https://github.com/s3proxy-distro/helm-s3proxy>
* <https://github.com/s3proxy-distro/container-s3proxy>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `100` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| config.env | list | `[]` |  |
| config.jclouds.filesystem.baseDir | string | `"/data"` |  |
| config.jclouds.filesystem.tmpSize | string | `"500Mi"` |  |
| config.jclouds.provider | string | `"filesystem"` |  |
| config.s3proxy.authorization | string | `"aws-v2-or-v4"` |  |
| config.s3proxy.ignoreUnknownHeaders | bool | `false` |  |
| config.s3proxy.readOnlyBlobStore | bool | `false` |  |
| config.s3proxy.v4MaxNonChunkedRequestSize | string | `"33554432"` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"ghcr.io/s3proxy-distro/containers/container-s3proxy-eclipse-temurin-11"` |  |
| image.tag | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations | object | `{}` |  |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.tls | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext.fsGroup | int | `10001` |  |
| podSecurityContext.fsGroupChangePolicy | string | `"OnRootMismatch"` |  |
| podSecurityContext.runAsGroup | int | `10001` |  |
| podSecurityContext.runAsNonRoot | bool | `true` |  |
| podSecurityContext.runAsUser | int | `10001` |  |
| podSecurityContext.seccompProfile.type | string | `"RuntimeDefault"` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| securityContext.allowPrivilegeEscalation | bool | `false` |  |
| securityContext.capabilities.drop[0] | string | `"ALL"` |  |
| securityContext.readOnlyRootFilesystem | bool | `true` |  |
| service.port | int | `8080` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| tolerations | list | `[]` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.3](https://github.com/norwoodj/helm-docs/releases/v1.11.3)
