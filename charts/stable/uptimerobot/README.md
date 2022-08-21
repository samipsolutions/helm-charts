# uptimerobot

![Version: 3.0.4](https://img.shields.io/badge/Version-3.0.4-informational?style=flat-square) ![AppVersion: 1.1.0](https://img.shields.io/badge/AppVersion-1.1.0-informational?style=flat-square)

A tool to get statistics from Uptime Robot and log it into InfluxDB

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/samipsolutions/helm-charts/issues/new/choose)**

## Source Code

* <https://github.com/trojanc/node-influx-uptimerobot>
* <https://github.com/samipsolutions/helm-charts>

## Requirements

## Dependencies

| Repository | Name | Version |
|------------|------|---------|

## TL;DR

```console
helm repo add k8s-at-home https://helm.samipsolutions.fi/
helm repo update
helm install uptimerobot k8s-at-home/uptimerobot
```

## Installing the Chart

To install the chart with the release name `uptimerobot`

```console
helm install uptimerobot k8s-at-home/uptimerobot
```

## Uninstalling the Chart

To uninstall the `uptimerobot` deployment

```console
helm uninstall uptimerobot
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install uptimerobot \
  --set env.TZ="America/New York" \
    k8s-at-home/uptimerobot
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install uptimerobot k8s-at-home/uptimerobot -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| config.influxdb.database | string | `"uptimerobot"` |  |
| config.influxdb.host | string | `"influxdb-influxdb"` | host/port/database are mandatory - change as needed |
| config.influxdb.port | int | `8086` |  |
| config.influxdb.protocol | string | `"http"` |  |
| config.uptimerobot.apikey | string | `"someapikey"` | uptimerobot API key (REQUIRED) |
| delay | int | `300` | number of seconds to wait between collections |
| image.pullPolicy | string | `"Always"` | uptimerobot image pull policy |
| image.repository | string | `"billimek/node-influx-uptimerobot"` | uptimerobot image |
| image.tag | string | `"latest"` | uptimerobot image tag |
| nodeSelector | object | `{}` |  choice for the user. This also increases chances charts run on environments with little resources, such as Minikube. If you do want to specify resources, uncomment the following lines, adjust them as necessary, and remove the curly braces after 'resources:'. limits:  cpu: 100m  memory: 128Mi requests:  cpu: 100m  memory: 128Mi |
| podAnnotations | object | `{}` | Key-value pairs to add as pod annotations |
| replicaCount | int | `1` |  This is a YAML-formatted file. Declare variables to be passed into your templates. |
| resources | object | `{}` |  |

## Changelog

### Version 3.0.4

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/k8s-at-home/uptimerobot?modal=changelog)

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/samipsolutions/helm-charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/k8s-at-home/helm-docs/releases/v0.1.1)