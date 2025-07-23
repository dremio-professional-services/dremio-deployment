# AWS EKS Auto Mode Deployment

Use the CloudFormation templates to do an EKS cluster deployment.

Following disks are provisioned by default:
- 1x Coordinator disk: 512GB io2 with 6000 IOPS
- 3x MongoDB disk: 256GB io2 with 6000 IOPS
- 3x OpenSearch disk: 256GB io2 with 6000 IOPS
- 3x Zookeeper disk: 8GB gp3
- 3x NATS disk: 8GB gp3
- 1x coordinator logs disk: 64GB gp3
- <n>x logs disk: 8GB gp3

Graviton instance types:
- General: 3x m6g.4xlarge (NATS, Zookeeper, MongoDB, OpenSearch)
- Coordinator: 1x r6gd.4xlarge or m6gd.8xlarge
- Executor: <n>x r6gd.4xlarge or m6gd.8xlarge

If the customer prefers x86 intel use: aws-eks-auto-mode-node-pools-x86.yml
Generally, Graviton instances provide a better cost and performance ratio.
    
Run the following commands to deploy the storage classes and node pools. 
Please change the zone in before applying it: `aws-eks-auto-mode-node-pools-graviton.yml`

```
kubectl apply -f aws-eks-auto-mode-node-pools-graviton.yml
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
helm upgrade --install dremio oci://quay.io/dremio/dremio-helm:3.1.0 -f values-aws-eks-auto-mode-v26.0.2.yml -f values-aws-eks-auto-mode-v26.0.2-override.yml
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
helm upgrade --install dremio oci://quay.io/dremio/dremio-helm:3.1.0 -f dremio-deployment\aws-eks-auto-mode\values-aws-eks-auto-mode-v26.0.2.yml -f dremio-deployment\my\values-aws-eks-auto-mode-v26.0.2-override.yml
```

