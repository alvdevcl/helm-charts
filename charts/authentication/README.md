# grafana-agent-operator

![Version: 0.3.21](https://img.shields.io/badge/Version-0.3.21-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.40.4](https://img.shields.io/badge/AppVersion-0.40.4-informational?style=flat-square)

A Helm chart for Alveo Authentication Service

⚠️  **Please create issues relating to this Helm chart in the [Agent](https://github.com/alvdevcl/authentication/issues) repo.**

## Source Code

* <https://github.com/alvdevcl/authentication/tree/v0.40.4/pkg/operator>




## Get Repo Info

```console
helm repo add alveo-helm-charts https://alvdevcl.github.io/helm-charts
helm repo update
```

_See [helm repo](https://helm.sh/docs/helm/helm_repo/) for command documentation._

## Installing the Chart

To install the chart with the release name `my-release`:

```console
helm install my-release alveo-helm-charts/authentication
```

## Uninstalling the Chart

To uninstall/delete the my-release deployment:

```console
helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Upgrading an existing Release to a new major version

A major chart version change (like v1.2.3 -> v2.0.0) indicates that there is an incompatible breaking change needing manual actions. Until this chart's version reaches `v1.0`, there are no promises of backwards compatibility.

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Pod affinity configuration |
| annotations | object | `{}` | Annotations for the Deployment |
| containerSecurityContext | object | `{}` | Container security context (allowPrivilegeEscalation, etc.) |
| extraArgs | list | `[]` | List of additional cli arguments to configure agent-operator (example: `--log.level`) |
| fullnameOverride | string | `""` | Overrides the chart's computed fullname |
| hostAliases | list | `[]` | hostAliases to add |
| image.pullPolicy | string | `"IfNotPresent"` | Image pull policy |
| image.pullSecrets | list | `[]` | Image pull secrets |
| image.registry | string | `"docker.io"` | Image registry |
| image.repository | string | `"grafana/agent-operator"` | Image repo |
| image.tag | string | `"v0.40.4"` | Image tag |
| kubeletService | object | `{"namespace":"default","serviceName":"kubelet"}` | If both are set, Agent Operator will create and maintain a service for scraping kubelets https://grafana.com/docs/agent/latest/operator/getting-started/#monitor-kubelets |
| nameOverride | string | `""` | Overrides the chart's name |
| nodeSelector | object | `{}` | nodeSelector configuration |
| podAnnotations | object | `{}` | Annotations for the Deployment Pods |
| podLabels | object | `{}` | Annotations for the Deployment Pods |
| podSecurityContext | object | `{}` | Pod security context (runAsUser, etc.) |
| rbac.create | bool | `true` | Toggle to create ClusterRole and ClusterRoleBinding |
| rbac.podSecurityPolicyName | string | `""` | Name of a PodSecurityPolicy to use in the ClusterRole. If unset, no PodSecurityPolicy is used. |
| resources | object | `{}` | Resource limits and requests config |
| serviceAccount.create | bool | `true` | Toggle to create ServiceAccount |
| serviceAccount.name | string | `nil` | Service account name |
| test.image.registry | string | `"docker.io"` | Test image registry |
| test.image.repository | string | `"library/busybox"` | Test image repo |
| test.image.tag | string | `"latest"` | Test image tag |
| tolerations | list | `[]` | Tolerations applied to Pods |