# kubernetes-jenkins-scripts

This repository contains Kubernetes manifests for deploying Jenkins on a Kubernetes cluster. The setup includes all necessary components for a production-ready Jenkins installation.

## Components

- `deployment.yaml` - Jenkins deployment configuration
- `service.yaml` - Service configuration for accessing Jenkins
- `pvc.yaml` - Persistent Volume Claim for Jenkins data persistence
- `ingress.yaml` - Ingress configuration for external access
- `values-jenkins.yaml` - Jenkins configuration values
- `Dockerfile` - Custom Jenkins Docker image configuration

## Prerequisites

- Kubernetes cluster
- kubectl configured to communicate with your cluster
- Storage class configured in your cluster for PVC
- Ingress controller installed in your cluster

## Installation

1. Clone this repository:
```bash
git clone https://