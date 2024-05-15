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
