# AWS EKS Auto Mode Deployment

Use the CloudFormation templates to do an EKS cluster deployment.

Run the following commands to deploy the storage classes and node pools. If you want to modify the zones change it in `aws-eks-auto-mode-node-pools.yml`
```
kubectl apply -f aws-eks-auto-mode-node-pools.yml
kubectl apply -f aws-eks-auto-mode-storage-classes.yml
```

Copy and use the following file `values-aws-eks-auto-mode-v26.0.2-override.yml` as a template. Do NOT modify `values-aws-eks-auto-mode-v26.0.2.yml`.
```
helm upgrade --install dremio charts\dremio\ -f values-aws-eks-auto-mode-v26.0.2.yml -f values-aws-eks-auto-mode-v26.0.2-override.yml
```


## Carsten's commands
```
kubectl apply -f dremio-deployment\aws-eks-auto-mode\aws-eks-auto-mode-node-pools.yml
kubectl apply -f dremio-deployment\aws-eks-auto-mode\aws-eks-auto-mode-storage-classes.yml
helm upgrade --install dremio helm-charts-v3\charts\dremio\ -f dremio-deployment\aws-eks-auto-mode\values-aws-eks-auto-mode-v26.0.2.yml -f dremio-deployment\my\values-aws-eks-auto-mode-v26.0.2-override.yml
```