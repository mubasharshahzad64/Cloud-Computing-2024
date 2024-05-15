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
  ```
 ```bash
   sudo apt-get update
   sudo apt-get install -y kubectl
   kubectl version --client
```
### 3. Install Minikube:
wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
chmod +x minikube-linux-amd64
sudo mv minikube-linux-amd64 /usr/local/bin/minikube
minikube start
minikube status
### 4. Docker driver, install Docker:
```
sudo apt update
sudo apt install -y docker.io
```
### 5. Verify Helm Installation
```
wget https://get.helm.sh/helm-v3.7.1-linux-amd64.tar.gz
tar -zxvf helm-v3.7.1-linux-amd64.tar.gz
sudo mv linux-amd64/helm /usr/local/bin/
helm version
```
## Installing Helm Charts
To install a Helm chart onto your Kubernetes cluster, follow these steps:
Download Helm chart:
```
helm install cloud-file-storage-chart .
The chart directory structure should be as follows:
cloud-file-storage-chart/
├── charts/
├── templates/
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── persistentvolume.yaml
│   ├── persistentvolumeclaim.yaml
│   └── configmap.yaml
└── values.yaml
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
### 1. Create Pods
### 2. Create YAML files for your Kubernetes resources (pods, deployments, services, etc.).
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
### 3. Apply Manifests
```
kubectl apply -f pod.yaml
kubectl apply -f persistentvolume.yaml
kubectl apply -f persistentvolumeclaim.yaml
kubectl apply -f service.yaml
kubectl apply -f deployment.yaml
```
### 4. Verify Deployment:
```
kubectl get pods
kubectl get services
kubectl get persistentvolumes
kubectl get persistentvolumeclaims
kubectl get deployments
```
Now i have a functioning Kubernetes cluster with Minikube, Helm installed, and applications deployed.
