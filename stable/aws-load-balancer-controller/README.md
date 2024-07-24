# aws-load-balancer-controller

![Version: 1.8.1](https://img.shields.io/badge/Version-1.8.1-informational?style=flat-square) ![AppVersion: v2.8.1](https://img.shields.io/badge/AppVersion-v2.8.1-informational?style=flat-square)

AWS Load Balancer Controller Helm chart for Kubernetes

**Homepage:** <https://github.com/aws/eks-charts>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| kishorj | <kishorj@users.noreply.github.com> | <https://github.com/kishorj> |
| m00nf1sh | <m00nf1sh@users.noreply.github.com> | <https://github.com/m00nf1sh> |

## Source Code

* <https://github.com/aws/eks-charts>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| additionalLabels | object | `{}` | Labels to add to each object of the chart. |
| affinity | object | `{}` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `5` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| awsApiEndpoints | string | `nil` |  |
| awsApiThrottle | string | `nil` |  |
| awsMaxRetries | string | `nil` |  |
| backendSecurityGroup | string | `nil` |  |
| certDiscovery.allowedCertificateAuthorityARNs | string | `""` |  |
| cluster.dnsDomain | string | `"cluster.local"` |  |
| clusterName | string | `nil` |  |
| clusterSecretsPermissions.allowAllSecrets | bool | `false` |  |
| configureDefaultAffinity | bool | `true` |  |
| controllerConfig.featureGates | object | `{}` |  |
| createIngressClassResource | bool | `true` |  |
| defaultSSLPolicy | string | `nil` |  |
| defaultTags | object | `{}` |  |
| defaultTargetType | string | `"instance"` |  |
| deploymentAnnotations | object | `{}` |  |
| disableIngressClassAnnotation | string | `nil` |  |
| disableIngressGroupNameAnnotation | string | `nil` |  |
| disableRestrictedSecurityGroupRules | string | `nil` |  |
| dnsPolicy | string | `nil` |  |
| enableBackendSecurityGroup | string | `nil` |  |
| enableCertManager | bool | `false` |  |
| enableEndpointSlices | string | `nil` |  |
| enablePodReadinessGateInject | string | `nil` |  |
| enableServiceMutatorWebhook | bool | `true` |  |
| enableShield | string | `nil` |  |
| enableWaf | string | `nil` |  |
| enableWafv2 | string | `nil` |  |
| env | string | `nil` |  |
| envFrom | string | `nil` |  |
| externalManagedTags | list | `[]` |  |
| extraVolumeMounts | string | `nil` |  |
| extraVolumes | string | `nil` |  |
| fullnameOverride | string | `""` |  |
| hostNetwork | bool | `false` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"public.ecr.aws/eks/aws-load-balancer-controller"` |  |
| image.tag | string | `"v2.8.1"` |  |
| imagePullSecrets | list | `[]` |  |
| ingressClass | string | `"alb"` |  |
| ingressClassConfig.default | bool | `false` |  |
| ingressClassParams.create | bool | `true` |  |
| ingressClassParams.name | string | `nil` |  |
| ingressClassParams.spec | object | `{}` |  |
| ingressMaxConcurrentReconciles | string | `nil` |  |
| keepTLSSecret | bool | `true` |  |
| livenessProbe.failureThreshold | int | `2` |  |
| livenessProbe.httpGet.path | string | `"/healthz"` |  |
| livenessProbe.httpGet.port | int | `61779` |  |
| livenessProbe.httpGet.scheme | string | `"HTTP"` |  |
| livenessProbe.initialDelaySeconds | int | `30` |  |
| livenessProbe.timeoutSeconds | int | `10` |  |
| loadBalancerClass | string | `nil` |  |
| logLevel | string | `nil` |  |
| metricsBindAddr | string | `""` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| objectSelector.matchExpressions | string | `nil` |  |
| objectSelector.matchLabels | string | `nil` |  |
| podAnnotations | object | `{}` |  |
| podDisruptionBudget | object | `{}` |  |
| podLabels | object | `{}` |  |
| podSecurityContext.fsGroup | int | `65534` |  |
| priorityClassName | string | `"system-cluster-critical"` |  |
| rbac.create | bool | `true` |  |
| readinessProbe.failureThreshold | int | `2` |  |
| readinessProbe.httpGet.path | string | `"/readyz"` |  |
| readinessProbe.httpGet.port | int | `61779` |  |
| readinessProbe.httpGet.scheme | string | `"HTTP"` |  |
| readinessProbe.initialDelaySeconds | int | `10` |  |
| readinessProbe.successThreshold | int | `1` |  |
| readinessProbe.timeoutSeconds | int | `10` |  |
| region | string | `nil` |  |
| replicaCount | int | `2` |  |
| resources | object | `{}` |  |
| revisionHistoryLimit | int | `10` |  |
| runtimeClassName | string | `""` |  |
| securityContext.allowPrivilegeEscalation | bool | `false` |  |
| securityContext.readOnlyRootFilesystem | bool | `true` |  |
| securityContext.runAsNonRoot | bool | `true` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.automountServiceAccountToken | bool | `true` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.imagePullSecrets | string | `nil` |  |
| serviceAccount.name | string | `nil` |  |
| serviceAnnotations | object | `{}` |  |
| serviceMaxConcurrentReconciles | string | `nil` |  |
| serviceMonitor.additionalLabels | object | `{}` |  |
| serviceMonitor.enabled | bool | `false` |  |
| serviceMonitor.interval | string | `"1m"` |  |
| serviceMonitor.metricRelabelings | string | `nil` |  |
| serviceMonitor.namespace | string | `nil` |  |
| serviceMonitor.relabelings | string | `nil` |  |
| serviceMonitor.scrapeTimeout | string | `nil` |  |
| serviceMutatorWebhookConfig.failurePolicy | string | `"Fail"` |  |
| serviceMutatorWebhookConfig.objectSelector.matchExpressions | list | `[]` |  |
| serviceMutatorWebhookConfig.objectSelector.matchLabels | object | `{}` |  |
| serviceMutatorWebhookConfig.operations[0] | string | `"CREATE"` |  |
| serviceTargetENISGTags | string | `nil` |  |
| syncPeriod | string | `nil` |  |
| targetgroupbindingMaxConcurrentReconciles | string | `nil` |  |
| targetgroupbindingMaxExponentialBackoffDelay | string | `nil` |  |
| terminationGracePeriodSeconds | int | `10` |  |
| tolerateNonExistentBackendAction | string | `nil` |  |
| tolerateNonExistentBackendService | string | `nil` |  |
| tolerations | list | `[]` |  |
| topologySpreadConstraints | object | `{}` |  |
| updateStrategy | object | `{}` |  |
| vpcId | string | `nil` |  |
| watchNamespace | string | `nil` |  |
| webhookBindPort | string | `nil` |  |
| webhookNamespaceSelectors | string | `nil` |  |
| webhookTLS.caCert | string | `nil` |  |
| webhookTLS.cert | string | `nil` |  |
| webhookTLS.key | string | `nil` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.13.1](https://github.com/norwoodj/helm-docs/releases/v1.13.1)
