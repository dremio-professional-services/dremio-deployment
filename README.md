# Dremio Deployment

Standardized deployment configurations for Dremio v26.x on Azure AKS and AWS EKS Auto Mode.

## Overview

This repository provides production-ready Helm chart configurations and deployment guides for deploying Dremio on Kubernetes across major cloud providers. The main goal is to standardize Azure and AWS deployments with Dremio v26.x, ensuring consistent, reliable, and optimized configurations.

## Deployment Targets

### Azure AKS
Comprehensive deployment guide for Azure Kubernetes Service with support for:
- ARM and Intel instance types
- Zone-redundant (ZRS) and local-redundant (LRS) storage configurations
- Local NVMe disk provisioning
- Prometheus monitoring integration

📖 **[Azure AKS Deployment Guide](azure-aks/README.md)**

### AWS EKS Auto Mode
Complete deployment guide for AWS EKS Auto Mode with:
- CloudFormation templates for cluster provisioning
- Graviton (ARM) and Intel x86 instance support
- Karpenter-based auto-scaling
- Full and Light deployment modes

📖 **[AWS EKS Auto Mode Deployment Guide](aws-eks-auto-mode/README.md)**

## Deployment Modes

Both platforms support two deployment configurations:

- **Full**: Complete Dremio deployment including all components (Catalog, MongoDB, OpenSearch, NATS, Zookeeper) with production sizing
- **Light**: Classic deployment without semantic search and Dremio Catalog for simpler use cases

## Repository Structure

```
dremio-deployment/
├── azure-aks/              # Azure AKS deployment configurations
│   ├── README.md           # Detailed Azure deployment guide
│   ├── prometheus/         # Prometheus monitoring setup
│   └── benchmark/          # Disk performance benchmarks
├── aws-eks-auto-mode/      # AWS EKS Auto Mode configurations
│   ├── README.md           # Detailed AWS deployment guide
│   ├── cloudformation/     # CloudFormation templates
│   ├── kubernetes/         # Kubernetes manifests
│   └── benchmark/          # Disk performance benchmarks
└── helm-charts-v3/         # Helm chart source files
```

## Quick Start

1. Choose your cloud platform (Azure AKS or AWS EKS)
2. Follow the platform-specific README for detailed deployment instructions
3. Select your deployment mode (Full or Light)
4. Apply the provided configurations and Helm values

## Prerequisites

- Kubernetes 1.28+
- Helm v3
- Dremio Enterprise license
- Cloud provider CLI tools (Azure CLI or AWS CLI)

## Support

For detailed deployment instructions, troubleshooting, and configuration options, refer to the platform-specific README files linked above.

## Additional Resources

- [Dremio Documentation](https://docs.dremio.com/)
- [Dremio Website](https://www.dremio.com/)

