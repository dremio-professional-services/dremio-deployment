# AWS EKS Auto Mode Deployment

Use the CloudFormation templates to do an EKS cluster deployment.

Run the following commands to deploy the storage classes and node pools. If you want to modify the zones change it in `aws-eks-auto-mode-node-pools.yml`
```
kubectl apply -f aws-eks-auto-mode-node-pools.yml
kubectl apply -f aws-eks-auto-mode-storage-classes.yml
```

Create the catalog secret:
```
export AWS_ACCESS_KEY_ID=<access-key> 
export AWS_SECRET_ACCESS_KEY=<secret-key> 
kubectl create secret generic catalog-server-s3-storage-creds --namespace $NAMESPACE --from-literal awsAccessKeyId=$AWS_ACCESS_KEY_ID --from-literal awsSecretAccessKey=$AWS_SECRET_ACCESS_KEY
```

Copy and use the following file `values-aws-eks-auto-mode-v26.0.2-override.yml` as a template. Do NOT modify `values-aws-eks-auto-mode-v26.0.2.yml`.

```
helm upgrade --install dremio charts\dremio\ -f values-aws-eks-auto-mode-v26.0.2.yml -f values-aws-eks-auto-mode-v26.0.2-override.yml
```

## Add engines via UI and set the node selector:

```
karpenter.sh/nodepool: dremio-executor
```

## Carsten's commands
```
kubectl apply -f dremio-deployment\aws-eks-auto-mode\aws-eks-auto-mode-node-pools.yml
kubectl apply -f dremio-deployment\aws-eks-auto-mode\aws-eks-auto-mode-storage-classes.yml
helm upgrade --install dremio helm-charts-v3\charts\dremio\ -f dremio-deployment\aws-eks-auto-mode\values-aws-eks-auto-mode-v26.0.2.yml -f dremio-deployment\my\values-aws-eks-auto-mode-v26.0.2-override.yml
```

