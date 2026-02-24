# Dremio Prometheus Monitoring

### Initial Prometheus Setup

#### Create a Namespace for Prometheus
Create a Namespace for monitoring:

`kubectl create ns monitoring`

#### Install Metrics Server
In order to use the default scaling metrics of CPU and memory usage, [metrics server](https://github.com/kubernetes-sigs/metrics-server) will need to be installed
This step is not required for Azure Kubernetes Service (AKS).

```
# Add the kubernetes-sigs repo
helm repo add metrics-server https://kubernetes-sigs.github.io/metrics-server/

# Install Metrics Server
helm install  metrics-server metrics-server/metrics-server -n monitoring
```

#### Install Prometheus Stack
In order to have the required Custom Resource Definitions (CRD), we will need 
[Prometheus Stack](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack) installed.

Use the Prometheus stack template file values_prometheus_<K8s type>.79.9.0.yml and create a copy.
Walk through the file and replace all values which are marked with a 'TODO'. This includes node selectors, storage classes and hostnames.

```
# Add the prometheus-community repo
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update

# Install kube-prometheus-stack
helm upgrade --install prometheus prometheus-community/kube-prometheus-stack -n monitoring --version 79.9.0 -f values_prometheus.79.9.0.yml
```

#### Add pod monitors
To add the pod monitors so that Prometheus starts scraping the metrics from Dremio and Zookeeper, run the following command:
```
kubectl apply -n <dremio namespace> -f dremio-pod-monitors.yaml
```

#### Install the Grafana Dashboard

Login into Grafana and click the '+' icon at the top right and select "Import dashboard". Upload the file from this repository: [Dremio_Monitoring.json](./grafana/Dremio_Monitoring.json).