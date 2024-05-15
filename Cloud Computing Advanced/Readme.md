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

