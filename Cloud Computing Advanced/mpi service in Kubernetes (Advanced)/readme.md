# Running OSU Benchmarks in Kubernetes

This repository contains instructions and configurations for running OSU benchmarks inside two containers distributed across different nodes in a Kubernetes cluster.

## Introduction

This exercise aims to demonstrate proficiency in Kubernetes, Docker, and HPC workflows by porting simple HPC workflows into Kubernetes and testing their performance.

## Requirements

- A Kubernetes cluster with at least two nodes.
- Flannel or Calico installed for network communication between nodes.
- MPI operator installed in the cluster.

## Instructions

### 1. Set Up the Kubernetes Cluster

Ensure you have a Kubernetes cluster with at least two nodes. You can use a cloud provider like GKE, EKS, or AKS, or set up your own using tools like Minikube, kubeadm, or kind. Install Flannel or Calico for network communication between nodes.

### 2. Install MPI Operator

Install the MPI operator in your Kubernetes cluster by applying the YAML manifest provided in the [mpi-operator documentation](https://github.com/kubeflow/mpi-operator).

```bash
kubectl apply -f https://raw.githubusercontent.com/kubeflow/mpi-operator/v0.3.0/deploy/v1alpha2/mpi-operator.yaml
# Running OSU Benchmarks in Kubernetes

This repository contains instructions and configurations for running OSU benchmarks inside two containers distributed across different nodes in a Kubernetes cluster.

## Introduction

This exercise aims to demonstrate proficiency in Kubernetes, Docker, and HPC workflows by porting simple HPC workflows into Kubernetes and testing their performance.

## Requirements

To complete this exercise, you need:

- A Kubernetes cluster with at least two nodes.
- Flannel or Calico installed for network communication between nodes.
- MPI operator installed in the cluster.

## Instructions

### 1. Set Up the Kubernetes Cluster

Ensure you have a Kubernetes cluster with at least two nodes. You can use a cloud provider like GKE, EKS, or AKS, or set up your own using tools like Minikube, kubeadm, or kind. Install Flannel or Calico for network communication between nodes.

### 2. Install MPI Operator
```
Install the MPI operator in your Kubernetes cluster by applying the YAML manifest provided in the [mpi-operator documentation](https://github.com/kubeflow/mpi-operator).

```bash
```
### 3. kubectl apply -f https://raw.githubusercontent.com/kubeflow/mpi-operator/v0.3.0/deploy/v1alpha2/mpi-operator.yaml
Build the container image using the provided Dockerfile.
Push the image to a container registry accessible by your Kubernetes cluster.
### 4. Deploy MPI Job in Kubernetes
reate an MPI job YAML file using the MPI operator to run the OSU benchmark. Specify the number of replicas and resources required for the job.
# MPIJob YAML
```
apiVersion: kubeflow.org/v1alpha2
kind: MPIJob
metadata:
  name: osu-benchmark
spec:
  slotsPerWorker: 1
  cleanPodPolicy: Running
  mpiReplicaSpecs:
    Launcher:
      replicas: 1
      template:
        spec:
          containers:
            - name: mpi-launcher
              image: <your-dockerhub-username>/osu-benchmark:latest
              command: ["mpirun"]
              args: ["-n", "2", "-hostfile", "/etc/mpi/hostfile", "./pt2pt/osu_latency"]
              resources:
                limits:
                  cpu: 1
                  memory: 1Gi
    Worker:
      replicas: 2
      template:
        spec:
          containers:
            - name: mpi-worker
              image: <your-dockerhub-username>/osu-benchmark:latest
              resources:
                limits:
                  cpu: 1
                  memory: 1Gi
```
### 5. Verify and Measure Latency
kubectl logs -f $(kubectl get pods -l mpi_job_name=osu-benchmark -o name | grep launcher)
### 6. Compare Latency with Pods on the Same Node
### 7. Summary
By following these steps, you will:

-Set up a Kubernetes cluster with appropriate networking.
-Install the MPI operator.
-Create and deploy a container for the OSU benchmark.
-Measure and compare the latency between nodes and within the same node.
This exercise demonstrates my proficiency in Kubernetes, Docker, and handling HPC workflows.
