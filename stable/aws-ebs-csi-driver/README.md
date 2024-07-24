# aws-ebs-csi-driver

![Version: 2.31.0](https://img.shields.io/badge/Version-2.31.0-informational?style=flat-square) ![AppVersion: 1.31.0](https://img.shields.io/badge/AppVersion-1.31.0-informational?style=flat-square)

A Helm chart for AWS EBS CSI Driver

**Homepage:** <https://github.com/kubernetes-sigs/aws-ebs-csi-driver>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| ndegwajohn |  | <https://github.com/ndegwajohn> |

## Source Code

* <https://github.com/kubernetes-sigs/aws-ebs-csi-driver>

## Requirements

Kubernetes: `>=1.17.0-0`

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| additionalDaemonSets | string | `nil` |  |
| awsAccessSecret.accessKey | string | `"access_key"` |  |
| awsAccessSecret.keyId | string | `"key_id"` |  |
| awsAccessSecret.name | string | `"aws-secret"` |  |
| controller.additionalArgs | list | `[]` |  |
| controller.affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[0].preference.matchExpressions[0].key | string | `"eks.amazonaws.com/compute-type"` |  |
| controller.affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[0].preference.matchExpressions[0].operator | string | `"NotIn"` |  |
| controller.affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[0].preference.matchExpressions[0].values[0] | string | `"fargate"` |  |
| controller.affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution[0].weight | int | `1` |  |
| controller.affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[0].podAffinityTerm.labelSelector.matchExpressions[0].key | string | `"app"` |  |
| controller.affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[0].podAffinityTerm.labelSelector.matchExpressions[0].operator | string | `"In"` |  |
| controller.affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[0].podAffinityTerm.labelSelector.matchExpressions[0].values[0] | string | `"ebs-csi-controller"` |  |
| controller.affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[0].podAffinityTerm.topologyKey | string | `"kubernetes.io/hostname"` |  |
| controller.affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[0].weight | int | `100` |  |
| controller.batching | bool | `true` |  |
| controller.containerSecurityContext | object | `{"allowPrivilegeEscalation":false,"readOnlyRootFilesystem":true}` | - securityContext on the controller container (see sidecars for securityContext on sidecar containers) |
| controller.defaultFsType | string | `"ext4"` |  |
| controller.deploymentAnnotations | object | `{}` |  |
| controller.dnsConfig | object | `{}` |  |
| controller.enableMetrics | bool | `false` | - |
| controller.env | list | `[]` |  |
| controller.envFrom | list | `[]` |  |
| controller.extraCreateMetadata | bool | `true` |  |
| controller.extraVolumeTags | object | `{}` | - extraVolumeTags:   key1: value1   key2: value2 |
| controller.httpEndpoint | string | `nil` |  |
| controller.initContainers | list | `[]` |  |
| controller.k8sTagClusterId | string | `nil` | - ID of the Kubernetes cluster used for tagging provisioned EBS volumes (optional). |
| controller.logLevel | int | `2` |  |
| controller.loggingFormat | string | `"text"` |  |
| controller.nodeSelector | object | `{}` |  |
| controller.otelTracing | object | `{}` |  |
| controller.podAnnotations | object | `{}` |  |
| controller.podLabels | object | `{}` |  |
| controller.priorityClassName | string | `"system-cluster-critical"` |  |
| controller.region | string | `nil` | - region: us-east-1 |
| controller.replicaCount | int | `2` |  |
| controller.resources.limits.memory | string | `"256Mi"` |  |
| controller.resources.requests.cpu | string | `"10m"` |  |
| controller.resources.requests.memory | string | `"40Mi"` |  |
| controller.revisionHistoryLimit | int | `10` |  |
| controller.sdkDebugLog | bool | `false` |  |
| controller.securityContext.fsGroup | int | `1000` |  |
| controller.securityContext.runAsGroup | int | `1000` |  |
| controller.securityContext.runAsNonRoot | bool | `true` |  |
| controller.securityContext.runAsUser | int | `1000` |  |
| controller.serviceAccount.annotations | object | `{}` |  |
| controller.serviceAccount.automountServiceAccountToken | bool | `true` |  |
| controller.serviceAccount.create | bool | `true` |  |
| controller.serviceAccount.name | string | `"ebs-csi-controller-sa"` |  |
| controller.serviceMonitor.forceEnable | bool | `false` |  |
| controller.serviceMonitor.interval | string | `"15s"` |  |
| controller.serviceMonitor.labels.release | string | `"prometheus"` |  |
| controller.socketDirVolume.emptyDir | object | `{}` |  |
| controller.tolerations[0].key | string | `"CriticalAddonsOnly"` |  |
| controller.tolerations[0].operator | string | `"Exists"` |  |
| controller.tolerations[1].effect | string | `"NoExecute"` |  |
| controller.tolerations[1].operator | string | `"Exists"` |  |
| controller.tolerations[1].tolerationSeconds | int | `300` |  |
| controller.topologySpreadConstraints | list | `[]` |  |
| controller.updateStrategy.rollingUpdate.maxUnavailable | int | `1` |  |
| controller.updateStrategy.type | string | `"RollingUpdate"` |  |
| controller.userAgentExtra | string | `"helm"` |  |
| controller.volumeModificationFeature.enabled | bool | `false` |  |
| controller.volumeMounts | list | `[]` |  |
| controller.volumes | list | `[]` |  |
| customLabels | object | `{}` | Custom labels to add into metadata |
| defaultStorageClass.enabled | bool | `false` |  |
| fullnameOverride | string | `nil` |  |
| helmTester.enabled | bool | `true` |  |
| helmTester.image | string | `"gcr.io/k8s-staging-test-infra/kubekins-e2e:v20240311-b09cdeb92c-master"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"public.ecr.aws/ebs-csi-driver/aws-ebs-csi-driver"` |  |
| image.tag | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `nil` |  |
| node.additionalArgs | list | `[]` |  |
| node.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[0].matchExpressions[0].key | string | `"eks.amazonaws.com/compute-type"` |  |
| node.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[0].matchExpressions[0].operator | string | `"NotIn"` |  |
| node.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[0].matchExpressions[0].values[0] | string | `"fargate"` |  |
| node.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[0].matchExpressions[1].key | string | `"node.kubernetes.io/instance-type"` |  |
| node.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[0].matchExpressions[1].operator | string | `"NotIn"` |  |
| node.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[0].matchExpressions[1].values[0] | string | `"a1.medium"` |  |
| node.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[0].matchExpressions[1].values[1] | string | `"a1.large"` |  |
| node.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[0].matchExpressions[1].values[2] | string | `"a1.xlarge"` |  |
| node.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[0].matchExpressions[1].values[3] | string | `"a1.2xlarge"` |  |
| node.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution.nodeSelectorTerms[0].matchExpressions[1].values[4] | string | `"a1.4xlarge"` |  |
| node.containerSecurityContext | object | `{"privileged":true,"readOnlyRootFilesystem":true}` | - securityContext on the node container (see sidecars for securityContext on sidecar containers) |
| node.daemonSetAnnotations | object | `{}` |  |
| node.enableLinux | bool | `true` |  |
| node.enableWindows | bool | `false` |  |
| node.env | list | `[]` |  |
| node.envFrom | list | `[]` |  |
| node.hostNetwork | bool | `false` |  |
| node.kubeletPath | string | `"/var/lib/kubelet"` |  |
| node.logLevel | int | `2` |  |
| node.loggingFormat | string | `"text"` |  |
| node.nodeSelector | object | `{}` |  |
| node.otelTracing | object | `{}` |  |
| node.podAnnotations | object | `{}` |  |
| node.podLabels | object | `{}` |  |
| node.priorityClassName | string | `nil` |  |
| node.probeDirVolume.emptyDir | object | `{}` |  |
| node.reservedVolumeAttachments | string | `nil` |  |
| node.resources.limits.memory | string | `"256Mi"` |  |
| node.resources.requests.cpu | string | `"10m"` |  |
| node.resources.requests.memory | string | `"40Mi"` |  |
| node.revisionHistoryLimit | int | `10` |  |
| node.securityContext.fsGroup | int | `0` |  |
| node.securityContext.runAsGroup | int | `0` |  |
| node.securityContext.runAsNonRoot | bool | `false` |  |
| node.securityContext.runAsUser | int | `0` |  |
| node.serviceAccount.annotations | object | `{}` |  |
| node.serviceAccount.automountServiceAccountToken | bool | `true` |  |
| node.serviceAccount.create | bool | `true` |  |
| node.serviceAccount.name | string | `"ebs-csi-node-sa"` |  |
| node.tolerateAllTaints | bool | `true` |  |
| node.tolerations[0].effect | string | `"NoExecute"` |  |
| node.tolerations[0].operator | string | `"Exists"` |  |
| node.tolerations[0].tolerationSeconds | int | `300` |  |
| node.updateStrategy.rollingUpdate.maxUnavailable | string | `"10%"` |  |
| node.updateStrategy.type | string | `"RollingUpdate"` |  |
| node.volumeAttachLimit | string | `nil` |  |
| node.volumeMounts | list | `[]` |  |
| node.volumes | list | `[]` |  |
| proxy.http_proxy | string | `nil` |  |
| proxy.no_proxy | string | `nil` |  |
| sidecars.attacher.additionalArgs | list | `[]` |  |
| sidecars.attacher.additionalClusterRoleRules | list | `[]` |  |
| sidecars.attacher.env | list | `[]` |  |
| sidecars.attacher.image.pullPolicy | string | `"IfNotPresent"` |  |
| sidecars.attacher.image.repository | string | `"public.ecr.aws/eks-distro/kubernetes-csi/external-attacher"` |  |
| sidecars.attacher.image.tag | string | `"v4.5.1-eks-1-30-4"` |  |
| sidecars.attacher.leaderElection.enabled | bool | `true` |  |
| sidecars.attacher.logLevel | int | `2` |  |
| sidecars.attacher.resources | object | `{}` |  |
| sidecars.attacher.securityContext.allowPrivilegeEscalation | bool | `false` |  |
| sidecars.attacher.securityContext.readOnlyRootFilesystem | bool | `true` |  |
| sidecars.livenessProbe.additionalArgs | list | `[]` |  |
| sidecars.livenessProbe.image.pullPolicy | string | `"IfNotPresent"` |  |
| sidecars.livenessProbe.image.repository | string | `"public.ecr.aws/eks-distro/kubernetes-csi/livenessprobe"` |  |
| sidecars.livenessProbe.image.tag | string | `"v2.12.0-eks-1-30-4"` |  |
| sidecars.livenessProbe.resources | object | `{}` |  |
| sidecars.livenessProbe.securityContext.allowPrivilegeEscalation | bool | `false` |  |
| sidecars.livenessProbe.securityContext.readOnlyRootFilesystem | bool | `true` |  |
| sidecars.nodeDriverRegistrar.additionalArgs | list | `[]` |  |
| sidecars.nodeDriverRegistrar.env | list | `[]` |  |
| sidecars.nodeDriverRegistrar.image.pullPolicy | string | `"IfNotPresent"` |  |
| sidecars.nodeDriverRegistrar.image.repository | string | `"public.ecr.aws/eks-distro/kubernetes-csi/node-driver-registrar"` |  |
| sidecars.nodeDriverRegistrar.image.tag | string | `"v2.10.1-eks-1-30-4"` |  |
| sidecars.nodeDriverRegistrar.livenessProbe.exec.command[0] | string | `"/csi-node-driver-registrar"` |  |
| sidecars.nodeDriverRegistrar.livenessProbe.exec.command[1] | string | `"--kubelet-registration-path=$(DRIVER_REG_SOCK_PATH)"` |  |
| sidecars.nodeDriverRegistrar.livenessProbe.exec.command[2] | string | `"--mode=kubelet-registration-probe"` |  |
| sidecars.nodeDriverRegistrar.livenessProbe.initialDelaySeconds | int | `30` |  |
| sidecars.nodeDriverRegistrar.livenessProbe.periodSeconds | int | `90` |  |
| sidecars.nodeDriverRegistrar.livenessProbe.timeoutSeconds | int | `15` |  |
| sidecars.nodeDriverRegistrar.logLevel | int | `2` |  |
| sidecars.nodeDriverRegistrar.resources | object | `{}` |  |
| sidecars.nodeDriverRegistrar.securityContext.allowPrivilegeEscalation | bool | `false` |  |
| sidecars.nodeDriverRegistrar.securityContext.readOnlyRootFilesystem | bool | `true` |  |
| sidecars.provisioner.additionalArgs | list | `[]` |  |
| sidecars.provisioner.additionalClusterRoleRules | string | `nil` |  |
| sidecars.provisioner.env | list | `[]` |  |
| sidecars.provisioner.image.pullPolicy | string | `"IfNotPresent"` |  |
| sidecars.provisioner.image.repository | string | `"public.ecr.aws/eks-distro/kubernetes-csi/external-provisioner"` |  |
| sidecars.provisioner.image.tag | string | `"v4.0.1-eks-1-30-4"` |  |
| sidecars.provisioner.leaderElection.enabled | bool | `true` |  |
| sidecars.provisioner.logLevel | int | `2` |  |
| sidecars.provisioner.resources | object | `{}` |  |
| sidecars.provisioner.securityContext.allowPrivilegeEscalation | bool | `false` |  |
| sidecars.provisioner.securityContext.readOnlyRootFilesystem | bool | `true` |  |
| sidecars.resizer.additionalArgs | list | `[]` |  |
| sidecars.resizer.additionalClusterRoleRules | list | `[]` |  |
| sidecars.resizer.env | list | `[]` |  |
| sidecars.resizer.image.pullPolicy | string | `"IfNotPresent"` |  |
| sidecars.resizer.image.repository | string | `"public.ecr.aws/eks-distro/kubernetes-csi/external-resizer"` |  |
| sidecars.resizer.image.tag | string | `"v1.10.1-eks-1-30-4"` |  |
| sidecars.resizer.leaderElection.enabled | bool | `true` |  |
| sidecars.resizer.logLevel | int | `2` |  |
| sidecars.resizer.resources | object | `{}` |  |
| sidecars.resizer.securityContext.allowPrivilegeEscalation | bool | `false` |  |
| sidecars.resizer.securityContext.readOnlyRootFilesystem | bool | `true` |  |
| sidecars.snapshotter.additionalArgs | list | `[]` |  |
| sidecars.snapshotter.additionalClusterRoleRules | list | `[]` |  |
| sidecars.snapshotter.env | list | `[]` |  |
| sidecars.snapshotter.forceEnable | bool | `false` |  |
| sidecars.snapshotter.image.pullPolicy | string | `"IfNotPresent"` |  |
| sidecars.snapshotter.image.repository | string | `"public.ecr.aws/eks-distro/kubernetes-csi/external-snapshotter/csi-snapshotter"` |  |
| sidecars.snapshotter.image.tag | string | `"v7.0.2-eks-1-30-4"` |  |
| sidecars.snapshotter.logLevel | int | `2` |  |
| sidecars.snapshotter.resources | object | `{}` |  |
| sidecars.snapshotter.securityContext.allowPrivilegeEscalation | bool | `false` |  |
| sidecars.snapshotter.securityContext.readOnlyRootFilesystem | bool | `true` |  |
| sidecars.volumemodifier.additionalArgs | list | `[]` |  |
| sidecars.volumemodifier.env | list | `[]` |  |
| sidecars.volumemodifier.image.pullPolicy | string | `"IfNotPresent"` |  |
| sidecars.volumemodifier.image.repository | string | `"public.ecr.aws/ebs-csi-driver/volume-modifier-for-k8s"` |  |
| sidecars.volumemodifier.image.tag | string | `"v0.3.0"` |  |
| sidecars.volumemodifier.leaderElection.enabled | bool | `true` |  |
| sidecars.volumemodifier.logLevel | int | `2` |  |
| sidecars.volumemodifier.resources | object | `{}` |  |
| sidecars.volumemodifier.securityContext.allowPrivilegeEscalation | bool | `false` |  |
| sidecars.volumemodifier.securityContext.readOnlyRootFilesystem | bool | `true` |  |
| storageClasses | list | `[]` |  |
| useOldCSIDriver | bool | `false` |  |
| volumeSnapshotClasses | list | `[]` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.13.1](https://github.com/norwoodj/helm-docs/releases/v1.13.1)
