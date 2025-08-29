# Kubernetes
## Ntosah77 Open Source Apps ##


# Introduction to Kubernetes and Minikube Setup on Debian

## 🚀 Introduction

Kubernetes (often abbreviated as K8s) is an open-source container orchestration system designed to automate deploying, scaling, and managing containerized applications. It simplifies the complexities of managing containerized workloads across clusters of machines, making it a cornerstone of modern cloud-native applications.

**Minikube** is a lightweight tool that allows you to run a single-node Kubernetes cluster locally on your machine. It's ideal for learning, testing, and developing Kubernetes applications without needing a cloud provider or a large infrastructure.

This guide walks you through installing **Minikube** on **Debian** to set up a local Kubernetes environment.

---

## 🧰 Prerequisites

Before proceeding, ensure your system meets the following requirements:

- **Debian** (e.g., Debian 11 or newer)
- At least **2 GB of RAM** (more is better for smoother performance)
- **VirtualBox** (required for Minikube)
- **Docker** (optional, but recommended for consistency with Kubernetes)
- Internet connectivity

---

## 🛠️ Installation Steps

### 1. Update Your System

```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Install VirtualBox

Minikube uses VirtualBox to run a local Kubernetes cluster. Install it using:

```bash
sudo apt install virtualbox -y
```

**Note:** If you already have VirtualBox installed, you may need to install the **VirtualBox Extension Pack** separately.

### 3. Install VirtualBox Extension Pack

1. Download the extension pack from [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads).
2. Extract the `.vbox-ext.zip` file.
3. Run the installer:

```bash
sudo VBoxManage extpack install <path_to_extension_pack>.vbox-ext.zip
```

### 4. Install kubectl (Kubernetes Command-Line Tool)

```bash
curl -LO "https://storage.googleapis.com/kubernetes-release/bin/v1.25.0/linux/amd64/kubectl"
sudo chmod +x kubectl
sudo mv kubectl /usr/local/bin/
For troubleshoting use
sudo rm /usr/local/bin/kubectl
```

Verify the installation:

```bash
kubectl version --client
```

### 5. Install Minikube

Download the latest Minikube binary:

```bash
curl -LO "https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64"
sudo chmod +x minikube-linux-amd64
sudo mv minikube-linux-amd64 /usr/local/bin/minikube
```

Verify the installation:

```bash
minikube version
```

### 6. Start Minikube

Start the local Kubernetes cluster:

```bash
minikube start
```

**Note:** This may take a few minutes to complete. It will automatically download and configure the necessary components.

---

## 🧪 Usage

Once Minikube is running, you can interact with your Kubernetes cluster using `kubectl`:

1. **Check Cluster Status:**

```bash
minikube status
```

2. **List Nodes:**

```bash
kubectl get nodes
```

3. **Check Minikube IP:**

```bash
minikube ip
```

4. **Access the Dashboard:**

```bash
minikube dashboard
```

---

## 🧪 Troubleshooting

- **Missing VirtualBox:** Ensure VirtualBox is installed and the Extension Pack is enabled.
- **Insufficient Resources:** Increase RAM or use a different driver (e.g., `--vm-driver=none` for Docker).
- **Permission Issues:** Use `sudo` for commands that require root access.
- **Minikube Not Starting:** Check the logs with `minikube logs`.

---

## 📝 Notes

- **Docker Compatibility:** Minikube uses Docker by default. If you prefer using VirtualBox, ensure Docker is installed or disable it.
- **Cluster Cleanup:** To stop and remove the cluster:

```bash
minikube stop
minikube delete
```

---

## 📚 Further Reading

- [Kubernetes Official Documentation](https://kubernetes.io/docs/)
- [Minikube GitHub Repository](https://github.com/kubernetes/minikube)
- [VirtualBox Extension Pack Download](https://www.virtualbox.org/wiki/Downloads)

---

## 🛠️ Conclusion

With Minikube installed on your Debian system, you're now ready to explore Kubernetes, develop applications, and experiment with container orchestration locally. This setup is a great starting point for learning and testing Kubernetes concepts. Happy coding! 
