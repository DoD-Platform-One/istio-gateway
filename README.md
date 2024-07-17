# gateway

![Version: 1.22.2-bb.0](https://img.shields.io/badge/Version-1.22.2--bb.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.22.2](https://img.shields.io/badge/AppVersion-1.22.2-informational?style=flat-square)

Helm chart for deploying Istio gateways

## Upstream References

* <https://github.com/istio/istio>

## Learn More
* [Application Overview](docs/overview.md)
* [Other Documentation](docs/)

## Pre-Requisites

* Kubernetes Cluster deployed
* Kubernetes config installed in `~/.kube/config`
* Helm installed

Install Helm

https://helm.sh/docs/intro/install/

## Deployment

* Clone down the repository
* cd into directory
```bash
helm install gateway chart/
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| image.repository | string | `"registry1.dso.mil/ironbank/opensource/istio/proxyv2"` |  |
| image.tag | string | `"1.22.2"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| defaults.name | string | `""` |  |
| defaults.revision | string | `""` |  |
| defaults.replicaCount | string | `nil` |  |
| defaults.kind | string | `"Deployment"` |  |
| defaults.rbac.enabled | bool | `true` |  |
| defaults.serviceAccount.create | bool | `true` |  |
| defaults.serviceAccount.annotations | object | `{}` |  |
| defaults.serviceAccount.name | string | `""` |  |
| defaults.podAnnotations."prometheus.io/port" | string | `"15020"` |  |
| defaults.podAnnotations."prometheus.io/scrape" | string | `"true"` |  |
| defaults.podAnnotations."prometheus.io/path" | string | `"/stats/prometheus"` |  |
| defaults.podAnnotations."inject.istio.io/templates" | string | `"gateway"` |  |
| defaults.podAnnotations."sidecar.istio.io/inject" | string | `"true"` |  |
| defaults.securityContext | object | `{}` |  |
| defaults.containerSecurityContext | object | `{}` |  |
| defaults.service.type | string | `"LoadBalancer"` |  |
| defaults.service.ports[0].name | string | `"status-port"` |  |
| defaults.service.ports[0].port | int | `15021` |  |
| defaults.service.ports[0].protocol | string | `"TCP"` |  |
| defaults.service.ports[0].targetPort | int | `15021` |  |
| defaults.service.ports[1].name | string | `"http2"` |  |
| defaults.service.ports[1].port | int | `80` |  |
| defaults.service.ports[1].protocol | string | `"TCP"` |  |
| defaults.service.ports[1].targetPort | int | `80` |  |
| defaults.service.ports[2].name | string | `"https"` |  |
| defaults.service.ports[2].port | int | `443` |  |
| defaults.service.ports[2].protocol | string | `"TCP"` |  |
| defaults.service.ports[2].targetPort | int | `443` |  |
| defaults.service.annotations | object | `{}` |  |
| defaults.service.loadBalancerIP | string | `""` |  |
| defaults.service.loadBalancerSourceRanges | list | `[]` |  |
| defaults.service.externalTrafficPolicy | string | `""` |  |
| defaults.service.externalIPs | list | `[]` |  |
| defaults.service.ipFamilyPolicy | string | `""` |  |
| defaults.service.ipFamilies | list | `[]` |  |
| defaults.resources.requests.cpu | string | `"100m"` |  |
| defaults.resources.requests.memory | string | `"128Mi"` |  |
| defaults.resources.limits.cpu | string | `"2000m"` |  |
| defaults.resources.limits.memory | string | `"1024Mi"` |  |
| defaults.autoscaling.enabled | bool | `true` |  |
| defaults.autoscaling.minReplicas | int | `1` |  |
| defaults.autoscaling.maxReplicas | int | `5` |  |
| defaults.autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| defaults.autoscaling.targetMemoryUtilizationPercentage | object | `{}` |  |
| defaults.autoscaling.autoscaleBehavior | object | `{}` |  |
| defaults.env | object | `{}` |  |
| defaults.labels | object | `{}` |  |
| defaults.annotations | object | `{}` |  |
| defaults.nodeSelector | object | `{}` |  |
| defaults.tolerations | list | `[]` |  |
| defaults.topologySpreadConstraints | list | `[]` |  |
| defaults.affinity | object | `{}` |  |
| defaults.networkGateway | string | `""` |  |
| defaults.imagePullPolicy | string | `""` |  |
| defaults.imagePullSecrets | list | `[]` |  |
| defaults.podDisruptionBudget | object | `{}` |  |
| defaults.terminationGracePeriodSeconds | int | `30` |  |
| defaults.volumes | list | `[]` |  |
| defaults.volumeMounts | list | `[]` |  |
| defaults.priorityClassName | string | `""` |  |

## Contributing

Please see the [contributing guide](./CONTRIBUTING.md) if you are interested in contributing.
