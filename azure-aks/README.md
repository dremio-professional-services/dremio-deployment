# Azure Kubernetes - AKS deployment

Deploy an AKS cluster with a standard small system pool (e.g. using UI).
Then add the following node pools. You can choose between ARM and Intel instance types.
The option "Node pool with ARM - 16x CPUs" is recommended, if you do not have any preference.

> WARNING!!!
> 
> Do NOT use any v6 instances since the behavior of the local NVMEs is different.
> 
> Do NOT use spot instances.

## Node pool with ARM - 16x CPUs (recommended)

- General: 3x Standard_D8s_v5 (NATS, Zookeeper, MongoDB, OpenSearch)
- Coordinator: 1x Standard_E16s_v5
- Executor: n-x Standard_E16pds_v5

> WARNING!!!  
> 
> If you want to create a zone-redundant cluster, you need to create the node pools in all 3 zones using: `--zones 1 2 3`. In this case you have to use the ZRS storage classes.
> 
> If you want to create a local-redundant cluster, you need to create the node pools in a single zone using: `--zones 1`. In this case you have to use the LRS storage classes.


```shell
az aks nodepool add --resource-group carsten-rg --cluster-name carsten-aks --name dremiocommon --mode User --node-count 1 --min-count 0 --max-count 5 --enable-cluster-autoscaler --node-vm-size Standard_D8ps_v5 --node-osdisk-type Managed --node-osdisk-size 128 --os-type Linux --os-sku AzureLinux --zones 1 2 3
az aks nodepool add --resource-group carsten-rg --cluster-name carsten-aks --name dremiocoord --mode User --node-count 1 --min-count 0 --max-count 5 --enable-cluster-autoscaler --node-vm-size Standard_E16ps_v5 --node-osdisk-type Managed --node-osdisk-size 128 --os-type Linux --os-sku AzureLinux --zones 1 2 3
az aks nodepool add --resource-group carsten-rg --cluster-name carsten-aks --name dremioexec --mode User --node-count 1 --min-count 0 --max-count 100 --enable-cluster-autoscaler --node-vm-size Standard_E16pds_v5 --node-osdisk-type Managed --node-osdisk-size 128 --os-type Linux --os-sku AzureLinux --zones 1 2 3
```

## Node pool with ARM - 32x CPUs

- General: 3x Standard_D8s_v5 (NATS, Zookeeper, MongoDB, OpenSearch)
- Coordinator: 1x Standard_E32ps_v5
- Executor: n-x Standard_E32pds_v5

```shell
az aks nodepool add --resource-group carsten-rg --cluster-name carsten-aks --name dremiocommon --mode User --node-count 1 --min-count 0 --max-count 5 --enable-cluster-autoscaler --node-vm-size Standard_D8ps_v5 --node-osdisk-type Managed --node-osdisk-size 128 --os-type Linux --os-sku AzureLinux --zones 1 2 3
az aks nodepool add --resource-group carsten-rg --cluster-name carsten-aks --name dremiocoord --mode User --node-count 1 --min-count 0 --max-count 5 --enable-cluster-autoscaler --node-vm-size Standard_E32ps_v5 --node-osdisk-type Managed --node-osdisk-size 128 --os-type Linux --os-sku AzureLinux --zones 1 2 3
az aks nodepool add --resource-group carsten-rg --cluster-name carsten-aks --name dremioexec --mode User --node-count 1 --min-count 0 --max-count 100 --enable-cluster-autoscaler --node-vm-size Standard_E32pds_v5 --node-osdisk-type Managed --node-osdisk-size 128 --os-type Linux --os-sku AzureLinux --zones 1 2 3
```

## Node pool with Intel - 16x CPUs

- General: 3x Standard_D8s_v5 (NATS, Zookeeper, MongoDB, OpenSearch)
- Coordinator: 1x Standard_E16s_v5
- Executor: n-x Standard_E16ds_v5

```shell
az aks nodepool add --resource-group carsten-rg --cluster-name carsten-aks --name dremiocommon --mode User --node-count 1 --min-count 0 --max-count 5 --enable-cluster-autoscaler --node-vm-size Standard_D8s_v5 --node-osdisk-type Managed --node-osdisk-size 128 --os-type Linux --os-sku AzureLinux --zones 1 2 3
az aks nodepool add --resource-group carsten-rg --cluster-name carsten-aks --name dremiocoord --mode User --node-count 1 --min-count 0 --max-count 5 --enable-cluster-autoscaler --node-vm-size Standard_E16s_v5 --node-osdisk-type Managed --node-osdisk-size 128 --os-type Linux --os-sku AzureLinux --zones 1 2 3
az aks nodepool add --resource-group carsten-rg --cluster-name carsten-aks --name dremioexec --mode User --node-count 1 --min-count 0 --max-count 100 --enable-cluster-autoscaler --node-vm-size Standard_E16ds_v5 --node-osdisk-type Managed --node-osdisk-size 128 --os-type Linux --os-sku AzureLinux --zones 1 2 3
```

## Node pool with Intel - 32x CPUs

- General: 3x Standard_D8s_v5 (NATS, Zookeeper, MongoDB, OpenSearch)
- Coordinator: 1x Standard_E32s_v5
- Executor: n-x Standard_E32ds_v5

```shell
az aks nodepool add --resource-group carsten-rg --cluster-name carsten-aks --name dremiocommon --mode User --node-count 1 --min-count 0 --max-count 5 --enable-cluster-autoscaler --node-vm-size Standard_D8s_v5 --node-osdisk-type Managed --node-osdisk-size 128 --os-type Linux --os-sku AzureLinux --zones 1 2 3
az aks nodepool add --resource-group carsten-rg --cluster-name carsten-aks --name dremiocoord --mode User --node-count 1 --min-count 0 --max-count 5 --enable-cluster-autoscaler --node-vm-size Standard_E32s_v5 --node-osdisk-type Managed --node-osdisk-size 128 --os-type Linux --os-sku AzureLinux --zones 1 2 3
az aks nodepool add --resource-group carsten-rg --cluster-name carsten-aks --name dremioexec --mode User --node-count 1 --min-count 0 --max-count 100 --enable-cluster-autoscaler --node-vm-size Standard_E32ds_v5 --node-osdisk-type Managed --node-osdisk-size 128 --os-type Linux --os-sku AzureLinux --zones 1 2 3
```

## Storage classes and disks

Following disks are provisioned by default:
- 1x Coordinator disk: 1024GB managed premium (5000 IOPS + 200 MB/s)
- 3x MongoDB disk: 1024GB managed premium (5000 IOPS + 200 MB/s)
- 3x OpenSearch disk: 512GB managed premium (2300 IOPS + 150 MB/s)
- 3x Zookeeper disk: 8GB standard (500 IOPS + 100 MB/s)
- 3x NATS disk: 8GB standard (500 IOPS + 100 MB/s)
- 1x coordinator logs disk: 64GB standard (500 IOPS + 100 MB/s)
- n-x logs disk: 8GB standard  (500 IOPS + 100 MB/s)

There are two types of storage classes:
- Zone-redudant storage classes (ZRS) -> azure-aks-storage-classes-zrs.yml
- Local-redundant storage classes (LRS) -> azure-aks-storage-classes-lrs.yml

Apply the storage classes by running the following command (choose one):

```shell
# Zone-redudant storage classes (ZRS) - Nodepools must be in three zones! (recommended)
kubectl apply -f azure-aks-storage-classes-zrs.yml
# Local-redundant storage classes (LRS) - Nodepools must be in only one zone!
kubectl apply -f azure-aks-storage-classes-lrs.yml
```

Create the catalog secret:
```
export AZURE_CLIENT_ID=<Azure App client id> 
export AZURE_CLIENT_SECRET=<App secret value> 
kubectl create secret generic catalog-server-azure-storage-creds --namespace default --from-literal azureClientId=$AZURE_CLIENT_ID --from-literal azureClientSecret=$AZURE_CLIENT_SECRET
```

Copy and use the following file `values-azure-aks-v26.0.2-override.yml` as a template. Do NOT modify `values-azure-aks-v26.0.2.yml`.

```
helm upgrade --install dremio oci://quay.io/dremio/dremio-helm:3.1.0 -f values-azure-aks-v26.0.2.yml -f values-azure-aks-v26.0.2-override.yml
```

## Add engines via UI and set the node selector:

```
nodepool: dremioexec
```

## Carsten's commands
```
kubectl apply -f .\dremio-deployment\azure-aks\azure-aks-storage-classes-lrs.yml
helm upgrade --install dremio oci://quay.io/dremio/dremio-helm:3.1.0 -f .\dremio-deployment\azure-aks\values-azure-aks-v26.0.2.yml -f dremio-deployment\my\values-azure-aks-v26.0.2-override.yml
```


