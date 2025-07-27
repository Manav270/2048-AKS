# AKS + INGRESS + 2048 Game Deployment

This project provisions an Azure Kubernetes Service (AKS) cluster and deploys the 2048 game behind a public-facing NGINX Ingress controller.

## 🧱 Components

- AKS cluster with random resource group and cluster name
- Helm-installed NGINX Ingress Controller
- 2048 game with Ingress routing

## 🚀 Quick Start

```bash
./scripts/deploy-aks.sh
