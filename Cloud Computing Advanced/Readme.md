# Cloud-Based File Storage System in Kubernetes.
# Setting up Kubernetes with Minikube on Windows

This guide explains how to set up a Kubernetes cluster using Minikube on a Windows operating system.

## Prerequisites

- VirtualBox installed (for running Minikube VM)
- Windows Subsystem for Linux (WSL) installed
- Docker installed on WSL
- `kubectl` installed on WSL

## Installing Kubernetes and Helm

### 1. Set up Minikube

First, install Minikube to create a local Kubernetes cluster.

```bash
# Download Minikube binary
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-windows-amd64.exe

# Move Minikube binary to your PATH
mv minikube-windows-amd64.exe /usr/local/bin/minikube
 Start Minikube
minikube start

#### 2. Install Helm

Helm is a package manager for Kubernetes.
# Download Helm binary
curl -LO https://get.helm.sh/helm-v3.7.1-windows-amd64.zip

# Unzip Helm binary
unzip helm-v3.7.1-windows-amd64.zip

# Move Helm binary to your PATH
mv windows-amd64/helm /usr/local/bin/helm

# Verify installation
helm version
Using Minikube
1. Start Minikube
minikube start
2. Verify Minikube status
minikube status
3. Run Minikube with Docker driver
minikube start --driver=docker
Deploying Applications with Helm
1. Search for Helm Charts
helm search repo wordpress
2. Install WordPress using Helm
helm install my-wordpress stable/wordpress
Creating Kubernetes Manifests
1. Create Pods
apiVersion: v1
kind: Pod
metadata:
  name: my-pod
spec:
  containers:
  - name: nginx
    image: nginx:latest
    ports:
    - containerPort: 80
2. Apply Manifests
kubectl apply -f my-pod.yaml

