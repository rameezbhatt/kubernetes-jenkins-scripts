# Kubernetes Jenkins Deployment

This repository contains Kubernetes manifests and configurations for deploying Jenkins on a Kubernetes cluster. The setup is designed for a production-ready environment, ensuring high availability, data persistence, and secure external access.

## 📦 Components

- **`deployment.yaml`**: Configures the Jenkins deployment, including pod templates and resource limits.
- **`service.yaml`**: Exposes Jenkins within the cluster or to external users via a NodePort or ClusterIP.
- **`pvc.yaml`**: Defines a Persistent Volume Claim to persist Jenkins data.
- **`ingress.yaml`**: Configures ingress rules for secure external access to Jenkins.
- **`values-jenkins.yaml`**: Contains configurable parameters for Jenkins deployment (e.g., admin credentials, plugins).
- **`Dockerfile`**: Builds a custom Jenkins Docker image with required tools, plugins, and configurations.

## 🛠 Prerequisites

Before deploying, ensure you have the following:

1. **Kubernetes Cluster**: A running cluster with sufficient resources.
2. **kubectl**: Configured to interact with your cluster.
3. **Storage Class**: Set up in your cluster for handling Persistent Volume Claims (PVCs).
4. **Ingress Controller**: Installed and functional (e.g., NGINX Ingress Controller or Traefik).

## 🚀 Installation

Follow these steps to deploy Jenkins on your Kubernetes cluster:

1. **Clone this repository**:
    ```bash
    git clone https://github.com/your-repo/kubernetes-jenkins-scripts.git
    cd kubernetes-jenkins-scripts
    ```

2. **Customize the configuration files**:
    - Modify `values-jenkins.yaml` to set desired values (e.g., Jenkins admin credentials, plugins).
    - Adjust `ingress.yaml` to match your domain and ingress controller settings.

3. **Apply the Kubernetes manifests**:
    ```bash
    kubectl apply -f pvc.yaml
    kubectl apply -f deployment.yaml
    kubectl apply -f service.yaml
    kubectl apply -f ingress.yaml
    ```

4. **Verify the deployment**:
    - Check the pods:
      ```bash
      kubectl get pods
      ```
    - Access Jenkins via the configured ingress domain or service IP.

## ⚙️ Customization

- **Custom Docker Image**:
  If you need additional plugins or tools, modify the `Dockerfile` and build your image:
  ```bash
  docker build -t your-custom-jenkins:latest .