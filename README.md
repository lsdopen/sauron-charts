# Sauron Collector

Installation

```
helm repo add sauron https://lsdopen.github.io/sauron-charts
helm repo update
```

```
helm install sauron/collector --set config.cluster.name="<Name of cluster>" --set --config.receiver.url="<URL of receiver>" --config.receiver.client_id="<Client ID for Receiver>" --config.receiver.client_secret="<Client Secret for Receiver>"
```
