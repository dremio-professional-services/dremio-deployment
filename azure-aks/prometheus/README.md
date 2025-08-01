# Dremio Prometheus Monitoring

### Initial Prometheus Setup

#### Create a Namespace for Prometheus
Create a Namespace for monitoring:

`kubectl create ns monitoring`

#### Install Prometheus Stack
In order to have the required Custom Resource Definitions (CRD), we will need 
[Prometheus Stack](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack) installed.

Use the Prometheus stack template file [values_prometheus.75.15.1.yml](./kube-prometheus-stack/values_prometheus.hc.55.7.0.yml) and create a copy.
Walk through the file and replace all values which are marked with a 'TODO'. This includes node selectors, storage classes and hostnames.

```
# Add the prometheus-community repo
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm update

# Install kube-prometheus-stack
helm upgrade --install prometheus prometheus-community/kube-prometheus-stack -n monitoring --version 75.15.1 -f values_prometheus.75.15.1.yml
```

#### Add pod monitors
To add the pod monitors so that Prometheus starts scraping the metrics from Dremio and Zookeeper, run the following command:
```
kubectl apply -n <dremio namespace> -f azure-aks-pod-monitors.yaml
```

#### Install the Grafana Dashboard

Login into Grafana and click the '+' icon at the top right and select "Import dashboard". Upload the file from this repository: [Dremio_Monitoring.json](./grafana/Dremio_Monitoring.json).