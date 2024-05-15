# Cloud-Based File Storage System in Kubernetes.
# Exercise Repository

This repository contains exercises related to setting up a Kubernetes cluster, installing Helm, and deploying applications using Minikube.

## Setting Up Kubernetes Cluster

### Prerequisites

- Windows operating system
- VirtualBox version 7.0
- Minikube

### Installation Steps

1. Create a VirtualBox VM with Ubuntu 20.04.
2. Install Kubernetes:
   ```bash
   sudo apt-get update
   sudo apt-get install -y kubectl
   kubectl version --client

### Deploying Applications with Helm
```
1. Search for Helm Charts
2. helm search repo wordpress
helm search repo wordpress
2. Install WordPress using Helm
3. helm install my-wordpress stable/wordpress
helm install my-wordpress stable/wordpress
```
### Creating Kubernetes Manifests
1. Create Pods
2. Create YAML files for your Kubernetes resources (pods, deployments, services, etc.).
```
apiVersion: v1
kind: Pod
metadata:
  name: mypod
spec:
  containers:
  - name: mycontainer
    image: nginx:latest
    ports:
    - containerPort: 80
    livenessProbe:
      httpGet:
        path: /
        port: 80
      initialDelaySeconds: 15
      periodSeconds: 10
    readinessProbe:
      httpGet:
        path: /
        port: 80
      initialDelaySeconds: 15
      periodSeconds: 10
```
### 2. Apply Manifests
```
kubectl apply -f my-pod.yaml
```
