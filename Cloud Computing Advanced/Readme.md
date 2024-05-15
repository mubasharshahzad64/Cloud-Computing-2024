# Cloud-Based File Storage System in Kubernetes.
# Setting up Kubernetes with Minikube

This guide explains how to set up a Kubernetes cluster using Minikube on a Linux operating system.

## 1. Install Minikube

First, install Minikube to create a local Kubernetes cluster.

```bash
# Download Minikube binary
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

# Move Minikube binary to your PATH
sudo mv minikube-linux-amd64 /usr/local/bin/minikube

# Make Minikube binary executable
sudo chmod +x /usr/local/bin/minikube

# Start Minikube
minikube start
```
## 2. Install Helm
Helm is a package manager for Kubernetes.
```
# Download Helm binary
curl -LO https://get.helm.sh/helm-v3.7.1-windows-amd64.zip

# Unzip Helm binary
unzip helm-v3.7.1-windows-amd64.zip

# Move Helm binary to your PATH
mv windows-amd64/helm /usr/local/bin/helm

# Verify installation
helm version
```
## Using Minikube
```
1. Start Minikube
minikube start
2. Verify Minikube status
minikube status
3. Run Minikube with Docker driver
minikube start --driver=docker
```
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
