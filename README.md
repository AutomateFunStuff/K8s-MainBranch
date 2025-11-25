# K8s-MainBranch
Overview

These scripts automate the setup of a Kubernetes cluster using kubeadm with containerd as the container runtime.

Components & Versions

Kubernetes: v1.34
Container Runtime: containerd v2.2.0
runc: v1.3.3
CNI Plugins: v1.6.0 (optional, commented out - Calico provides its own)
crictl: v1.34.0
Network Plugin: Calico
Scripts

common.sh

Common setup script for all nodes (control plane and worker nodes). This script:

Disables swap
Configures kernel modules (overlay, br_netfilter)
Sets up networking parameters
Installs containerd runtime
Installs and configures crictl
Installs kubelet, kubeadm, and kubectl
master.sh

Control plane (master) node setup script. This script:

Pulls required Kubernetes images
Initializes the control plane using kubeadm
Configures kubeconfig
Installs Calico network plugin