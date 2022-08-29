# Sauron Collector

## Installation

```
helm repo add sauron https://lsdopen.github.io/sauron-charts
helm repo update
```

```
helm install sauron/collector --set config.cluster.name="<Name of cluster>" --set config.receiver.url="<URL of receiver>" --set config.receiver.client_id="<Client ID for Receiver>" --set config.receiver.client_secret="<Client Secret for Receiver>"
```

## Parameters

### General

| Name                        | Description                                              | Value                      |
| --------------------------- | -------------------------------------------------------- | -------------------------- |
| `serviceAccount.create`     | defaults to true. Please do not change this.             | `true`                     |
| `image.repository`          | image repository to pull the image from.                 | `lsdtrip/sauron-collector` |
| `image.pullPolicy`          | image pull policy for container                          | `IfNotPresent`             |
| `image.tag`                 | image tag to use. Defaults to app version (recommended). | `""`                       |
| `resources.limits.cpu`      | CPU limits for container.                                | `200m`                     |
| `resources.limits.memory`   | Memory limits for container.                             | `256Mi`                    |
| `resources.requests.cpu`    | CPU request for container.                               | `50m`                      |
| `resources.requests.memory` | Memory requests for container.                           | `128Mi`                    |


### Proxy

| Name                | Description                                                   | Value   |
| ------------------- | ------------------------------------------------------------- | ------- |
| `proxy.enabled`     | If the Collector will be running behind a proxy, enable this. | `false` |
| `proxy.http_proxy`  | Proxy to use for http requests.                               | `""`    |
| `proxy.https_proxy` | Proxy to use for https requests.                              | `""`    |
| `proxy.no_proxy`    | Requests that should avoid using the proxy.                   | `""`    |


### Config

| Name                            | Description                                                | Value   |
| ------------------------------- | ---------------------------------------------------------- | ------- |
| `config.cluster.name`           | NB - Name of the cluster that the Collector will announce. | `""`    |
| `config.receiver.url`           | URL of Receiver.                                           | `""`    |
| `config.receiver.port`          | Port of Receiver.                                          | `443`   |
| `config.receiver.client_id`     | Client ID to authenticate to Receiver.                     | `""`    |
| `config.receiver.client_secret` | Client Secret to authenticate to Receiver.                 | `""`    |
| `config.log.level`              | Log level of Collector. Defaults to `error`.               | `error` |
| `config.log.console`            | Type of output. Defaults to structured logging if `false`. | `false` |

