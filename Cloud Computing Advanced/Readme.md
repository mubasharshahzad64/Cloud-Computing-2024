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
```

To add a second heading in your README.md file, you can simply use the Markdown syntax for headings, which is ##. You can place it wherever you want in the file. Here's how to add the second heading "Install Helm" after the first heading "Set up Minikube":

markdown
Copy code
# Setting up Kubernetes with Minikube on Windows

This guide explains how to set up a Kubernetes cluster using Minikube on a Windows operating system.

## 1. Set up Minikube

First, install Minikube to create a local Kubernetes cluster.

```bash
# Download Minikube binary
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-windows-amd64.exe

# Move Minikube binary to your PATH
mv minikube-windows-amd64.exe /usr/local/bin/minikube

# Start Minikube
minikube start
```
## 2. Install Helm
