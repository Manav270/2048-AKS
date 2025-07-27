# AKS + NGINX + 2048 Game Deployment

This project provisions an Azure Kubernetes Service (AKS) cluster and deploys the classic 2048 game behind a public-facing NGINX Ingress controller.

## 📁 Project Structure

```
aks-nginx-2048/
├── scripts/
│   └── deploy-aks.sh          # Main AKS + Helm + NGINX + app deployment script
├── manifests/
│   └── application_deployment.yaml  # Single YAML containing Namespace, Deployment, Service, and Ingress
├── README.md
```

## 🧱 Components

- Azure Resource Group (randomized name)
- AKS cluster with 1 node
- Helm-installed NGINX Ingress Controller
- 2048 game deployment in Kubernetes
- Path-based Ingress for app access

## 🚀 Quick Start

Ensure you have:
- Azure CLI
- kubectl
- Helm
- Bash shell with `openssl`

### Step 1: Run the Deployment Script

```bash
./scripts/deploy-aks.sh
```

This will:
- Provision an AKS cluster
- Install the NGINX Ingress Controller
- Deploy the 2048 game using `manifests/application_deployment.yaml`

### Step 2: Access the Application

Run the following to get the external IP of your NGINX controller:

```bash
kubectl get svc -n ingress-nginx ingress-nginx-controller
```

Example output:

```
ingress-nginx-controller   LoadBalancer   20.237.XXX.XXX   <pending>   80:xxxxx/TCP   5m
```

Open your browser to:

```
http://<EXTERNAL-IP>/
```

You should see the 2048 game interface!

---

## 🧼 Cleanup

To delete the resource group and all Azure resources:

```bash
az group delete --name <myAKSResourceGroupXXXX>
```

Enjoy the game! 🎮

