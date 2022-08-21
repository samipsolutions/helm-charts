# dokuwiki

![Version: 1.2.2](https://img.shields.io/badge/Version-1.2.2-informational?style=flat-square) ![AppVersion: 20200729.0.0](https://img.shields.io/badge/AppVersion-20200729.0.0-informational?style=flat-square)

DokuWiki is a simple to use and highly versatile Open Source wiki software that doesn't require a database.

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/samipsolutions/helm-charts/issues/new/choose)**

## Source Code

* <https://github.com/splitbrain/dokuwiki>
* <https://github.com/linuxserver/docker-dokuwiki>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://library-charts.k8s-at-home.com | common | 4.5.2 |

## TL;DR

```console
helm repo add k8s-at-home https://helm.samipsolutions.fi/
helm repo update
helm install dokuwiki k8s-at-home/dokuwiki
```

## Installing the Chart

To install the chart with the release name `dokuwiki`

```console
helm install dokuwiki k8s-at-home/dokuwiki
```

## Uninstalling the Chart

To uninstall the `dokuwiki` deployment

```console
helm uninstall dokuwiki
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install dokuwiki \
  --set env.TZ="America/New York" \
    k8s-at-home/dokuwiki
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install dokuwiki k8s-at-home/dokuwiki -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below (only deviations from the default settings are specified) | environment variables. See [image docs](https://docs.kanboard.org/en/latest/admin_guide/docker.html#environment-variables) and [application docs](# https://docs.kanboard.org/en/latest/admin_guide/config_file.html) for more details. |
| env.TZ | string | `"UTC"` | Application Timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"linuxserver/dokuwiki"` | image repository |
| image.tag | string | `"version-2020-07-29"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 1.2.2

#### Added

N/A

#### Changed

* Upgraded `common` chart dependency to version 4.5.2

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/k8s-at-home/dokuwiki?modal=changelog)

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/samipsolutions/helm-charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/k8s-at-home/helm-docs/releases/v0.1.1)