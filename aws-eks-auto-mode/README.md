# AWS EKS Auto Mode Deployment

Use the CloudFormation templates to do an EKS cluster deployment.You could deploy using either AWS console or cli. Sammple command for deploying usign cli:

## EKS Auto Mode Cluster deployment

Deployment via shell or AWS console.

```shell
aws cloudformation deploy \  --template-file eks-auto-mode-existing-vpc.yml \
  --stack-name dremio-eks-cluster \
  --capabilities CAPABILITY_NAMED_IAM \
  --parameter-overrides \
    UseSubnets='<subnetid1>,<subnetid2>' \
    EksVersion="1.32" \
    EksServiceIpv4Cidr="<vpc-cidr>" \
    EksPublicEndpoint="true"
```

## Deployment Modes

There are two modes of deployment:
- Full: Deployment including all Dremio components with production sizing
- Light: Classic deployment without semantic search and without Dremio Catalog

## Helm Chart deployment in an EKS Auto Mode cluster (Full deployment)

Following disks are provisioned by default:
- 1x Coordinator disk: 512GB io2 with 6000 IOPS
- 3x MongoDB disk: 256GB io2 with 6000 IOPS
- 3x OpenSearch disk: 256GB gp3 with 6000 IOPS
- 3x Zookeeper disk: 16GB gp3
- 3x NATS disk: 16GB gp3
- 1x coordinator logs disk: 256GB gp3
- <n>x logs disk: 16GB gp3

Graviton instance types:
- General: 4x m8g.2xlarge (NATS, Zookeeper, MongoDB, OpenSearch)
- Coordinator: 1x r8g.4xlarge or m8g.8xlarge
- Executor: <n>x r8gd.4xlarge or m8gd.8xlarge

Intel x86 instance types:
- General: 4x m5.2xlarge (NATS, Zookeeper, MongoDB, OpenSearch)
- Coordinator: 1x m5.4xlarge or m5.8xlarge
- Executor: <n>x r5d.4xlarge or m5d.8xlarge

If the customer prefers x86 intel use: aws-eks-auto-mode-node-pools-x86-full.yml
Generally, Graviton instances provide a better cost and performance ratio.
    
Run the following commands to deploy the storage classes and node pools. 
Please change the <ins>**availability zone (e.g. us-east-1a)**</ins> in before applying it: `aws-eks-auto-mode-node-pools-graviton.yml`

```
kubectl apply -f aws-eks-auto-mode-node-pools-graviton-full.yml
kubectl apply -f aws-eks-auto-mode-storage-classes.yml
```

Prerequisites to update alues-aws-eks-auto-mode-<helm version>-override.yml file.

* License  - https://docs.dremio.com/current/deploy-dremio/configuring-kubernetes/#license
* Pull Secret - https://docs.dremio.com/current/deploy-dremio/configuring-kubernetes/#pull-secret
* Coordinator's Distributed Storage - https://docs.dremio.com/current/deploy-dremio/configuring-kubernetes/#coordinators-distributed-storage
* Enterprise Catalog - https://docs.dremio.com/current/deploy-dremio/configuring-kubernetes/#enterprise-catalog


Create pod identity associations
```
aws eks create-pod-identity-association --cluster-name dremio-eks --namespace default --service-account dremio-catalog-services --role-arn arn:aws:iam::<AWS Account ID>:role/dremio-pod-identity --no-cli-pager --disable-session-tags
aws eks create-pod-identity-association --cluster-name dremio-eks --namespace default --service-account dremio-engine-executor --role-arn arn:aws:iam::<AWS Account ID>:role/dremio-pod-identity  --no-cli-pager --disable-session-tags
aws eks create-pod-identity-association --cluster-name dremio-eks --namespace default --service-account dremio-mongodb-operator --role-arn arn:aws:iam::<AWS Account ID>:role/dremio-pod-identity --no-cli-pager --disable-session-tags
aws eks create-pod-identity-association --cluster-name dremio-eks --namespace default --service-account dremio-catalog-server --role-arn arn:aws:iam::<AWS Account ID>:role/dremio-pod-identity --no-cli-pager --disable-session-tags
aws eks create-pod-identity-association --cluster-name dremio-eks --namespace default --service-account dremio-mongodb --role-arn arn:aws:iam::<AWS Account ID>:role/dremio-pod-identity --no-cli-pager --disable-session-tags
aws eks create-pod-identity-association --cluster-name dremio-eks --namespace default --service-account dremio-coordinator --role-arn arn:aws:iam::<AWS Account ID>:role/dremio-pod-identity --no-cli-pager --disable-session-tags
aws eks list-pod-identity-associations --cluster-name dremio-eks --no-cli-pager
```

Copy and use the following file `values-aws-eks-auto-mode-<helm version>-override.yml` as a template. Do NOT modify `values-aws-eks-auto-mode-<helm version>.yml`.

```
helm upgrade --install dremio oci://quay.io/dremio/dremio-helm:<helm version> -f values-aws-eks-auto-mode-<helm version>-v3.2.2-full-override.yml -f values-aws-eks-auto-mode-<helm version>-override.yml
```

## Add engines via UI and set the node selector:

```
karpenter.sh/nodepool: dremio-executor
```

## Carsten's commands
```
kubectl apply -f dremio-deployment\aws-eks-auto-mode\aws-eks-auto-mode-node-pools.yml
kubectl apply -f dremio-deployment\aws-eks-auto-mode\aws-eks-auto-mode-storage-classes.yml
helm upgrade --install dremio oci://quay.io/dremio/dremio-helm:3.2.0 -f dremio-deployment\aws-eks-auto-mode\values-aws-eks-auto-mode-v3.2.0.yml -f dremio-deployment\my\values-aws-eks-auto-mode-v3.2.0-full-carsten-eks.yml
helm upgrade dremio oci://quay.io/dremio/dremio-helm:3.2.0 -f dremio-deployment\aws-eks-auto-mode\values-aws-eks-auto-mode-v3.2.0.yml -f dremio-deployment\my\values-aws-eks-auto-mode-v3.2.0-full-carsten-eks.yml --set DremioAdmin=true --set catalog.replicas=0 --set catalog.externalAccess.replicas=0 --set catalogservices.replicas=0
```

