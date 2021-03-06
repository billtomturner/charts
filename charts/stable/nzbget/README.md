# nzbget

![Version: 10.1.0](https://img.shields.io/badge/Version-10.1.0-informational?style=flat-square) ![AppVersion: v21.0](https://img.shields.io/badge/AppVersion-v21.0-informational?style=flat-square)

NZBGet is a Usenet downloader client

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://nzbget.net/>
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
helm install nzbget k8s-at-home/nzbget
```

## Installing the Chart

To install the chart with the release name `nzbget`

```console
helm install nzbget k8s-at-home/nzbget
```

## Uninstalling the Chart

To uninstall the `nzbget` deployment

```console
helm uninstall nzbget
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install nzbget \
  --set env.TZ="America/New York" \
    k8s-at-home/nzbget
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install nzbget k8s-at-home/nzbget -f values.yaml
```

## Custom configuration

The default login details (change ASAP) are:

* login:nzbget
* password:tegbzn6789

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"ghcr.io/k8s-at-home/nzbget"` |  |
| image.tag | string | `"v21.0"` |  |
| ingress.enabled | bool | `false` |  |
| persistence.config.emptyDir.enabled | bool | `false` |  |
| persistence.config.enabled | bool | `false` |  |
| persistence.downloads.emptyDir.enabled | bool | `false` |  |
| persistence.downloads.enabled | bool | `false` |  |
| persistence.downloads.mountPath | string | `"/downloads"` |  |
| persistence.media.emptyDir.enabled | bool | `false` |  |
| persistence.media.enabled | bool | `false` |  |
| persistence.media.mountPath | string | `"/media"` |  |
| service.port.port | int | `6789` |  |
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
