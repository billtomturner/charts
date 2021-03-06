# qbittorrent

![Version: 10.1.0](https://img.shields.io/badge/Version-10.1.0-informational?style=flat-square) ![AppVersion: v4.3.4.1](https://img.shields.io/badge/AppVersion-v4.3.4.1-informational?style=flat-square)

qBittorrent is a cross-platform free and open-source BitTorrent client

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/qbittorrent/qBittorrent>
* <https://github.com/k8s-at-home/container-images>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://library-charts.k8s-at-home.com | common | 2.5.0 |

## TL;DR

```console
helm repo add k8s-at-home https://k8s-at-home.com/charts/
helm repo update
helm install qbittorrent k8s-at-home/qbittorrent
```

## Installing the Chart

To install the chart with the release name `qbittorrent`

```console
helm install qbittorrent k8s-at-home/qbittorrent
```

## Uninstalling the Chart

To uninstall the `qbittorrent` deployment

```console
helm uninstall qbittorrent
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install qbittorrent \
  --set env.TZ="America/New York" \
    k8s-at-home/qbittorrent
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install qbittorrent k8s-at-home/qbittorrent -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| additionalVolumeMounts[0].mountPath | string | `"/config/custom-cont-init.d"` |  |
| additionalVolumeMounts[0].name | string | `"qbittorrent-scripts"` |  |
| additionalVolumes[0].emptyDir | object | `{}` |  |
| additionalVolumes[0].name | string | `"qbittorrent-scripts"` |  |
| env | object | `{}` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"ghcr.io/k8s-at-home/qbittorrent"` |  |
| image.tag | string | `"v4.3.4.1"` |  |
| ingress.enabled | bool | `false` |  |
| persistence.config.emptyDir.enabled | bool | `false` |  |
| persistence.config.enabled | bool | `false` |  |
| persistence.downloads.emptyDir.enabled | bool | `false` |  |
| persistence.downloads.enabled | bool | `false` |  |
| persistence.downloads.mountPath | string | `"/downloads"` |  |
| persistence.media.emptyDir.enabled | bool | `false` |  |
| persistence.media.enabled | bool | `false` |  |
| persistence.media.mountPath | string | `"/media"` |  |
| service.additionalServices[0].enabled | bool | `true` |  |
| service.additionalServices[0].nameSuffix | string | `"bittorrent"` |  |
| service.additionalServices[0].port.name | string | `"bittorrent"` |  |
| service.additionalServices[0].port.port | int | `6881` |  |
| service.additionalServices[0].port.protocol | string | `"TCP"` |  |
| service.additionalServices[0].port.targetPort | int | `6881` |  |
| service.additionalServices[0].type | string | `"ClusterIP"` |  |
| service.port.port | int | `8080` |  |
| strategy.type | string | `"Recreate"` |  |

## Changelog

All notable changes to this application Helm chart will be documented in this file but does not include changes from our common library. To read those click [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common#changelog).

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

### [10.0.0]

#### Changed

- **Breaking**: swap linuxserver.io images for k8s@home image

### [1.0.0]

#### Added

- N/A

#### Changed

- N/A

#### Removed

- N/A

[10.0.0]: #10.0.0
[1.0.0]: #1.0.0

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
