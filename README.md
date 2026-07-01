# 🚀 Kubernetes Manifest 30-Day Challenge

Welcome to my **30-Day Kubernetes Manifest Challenge**!

This repository documents my journey of learning Kubernetes by writing manifest files every day for 30 days. The goal was to build a strong understanding of Kubernetes fundamentals by creating practical examples instead of only reading documentation.

Each day introduces a new Kubernetes concept, starting with Pods and gradually progressing to production-style application deployments.

---

## 🎯 Goals

- Learn Kubernetes by doing
- Practice writing YAML manifests from scratch
- Understand how Kubernetes resources work together
- Build a reusable reference repository
- Strengthen Kubernetes skills for DevOps and Cloud Engineering roles

---

## 📚 Challenge Roadmap

| Day | Topic |
|------|-------|
| Day 01 | Pod |
| Day 02 | Multi-Container Pod |
| Day 03 | Namespace |
| Day 04 | ReplicaSet |
| Day 05 | Deployment |
| Day 06 | Rolling Updates |
| Day 07 | Rollbacks |
| Day 08 | ClusterIP Service |
| Day 09 | NodePort Service |
| Day 10 | LoadBalancer Service |
| Day 11 | Multiple Pods Behind a Service |
| Day 12 | ConfigMap |
| Day 13 | Secret |
| Day 14 | ConfigMap and Secret |
| Day 15 | emptyDir Volume |
| Day 16 | hostPath Volume |
| Day 17 | PersistentVolume (PV) |
| Day 18 | PersistentVolumeClaim (PVC) |
| Day 19 | Pod with PersistentVolumeClaim |
| Day 20 | StorageClass |
| Day 21 | DaemonSet |
| Day 22 | StatefulSet |
| Day 23 | Headless Service |
| Day 24 | Job |
| Day 25 | CronJob |
| Day 26 | Resource Requests and Limits |
| Day 27 | Liveness and Readiness Probes |
| Day 28 | Startup Probe |
| Day 29 | Init Containers |
| Day 30 | Production-Style Kubernetes Application |

---

# 📂 Repository Structure

```text
.
├── README.md
├── Day - 01
│   ├── pod.yaml
│   └── README.md
├── Day - 02
│   ├── pod.yaml
│   └── README.md
├── Day - 03
│   ├── namespace.yaml
│   └── README.md
├── Day - 04
│   ├── replicaset.yaml
│   └── README.md
├── Day - 05
│   ├── deployment.yaml
│   └── README.md
├── Day - 06
│   ├── deployment.yaml
│   └── README.md
├── Day - 07
│   ├── deployment.yaml
│   └── README.md
├── Day - 08
│   ├── deployment.yaml
│   ├── service.yaml
│   └── README.md
├── Day - 09
│   ├── deployment.yaml
│   ├── service.yaml
│   └── README.md
├── Day - 10
│   ├── deployment.yaml
│   ├── service.yaml
│   └── README.md
├── Day - 11
│   ├── deployment.yaml
│   ├── service.yaml
│   └── README.md
├── Day - 12
│   ├── configmap.yaml
│   ├── pod.yaml
│   └── README.md
├── Day - 13
│   ├── secret.yaml
│   ├── pod.yaml
│   └── README.md
├── Day - 14
│   ├── configmap.yaml
│   ├── secret.yaml
│   ├── pod.yaml
│   └── README.md
├── Day - 15
│   ├── pod.yaml
│   └── README.md
├── Day - 16
│   ├── pod.yaml
│   └── README.md
├── Day - 17
│   ├── pv.yaml
│   └── README.md
├── Day - 18
│   ├── pv.yaml
│   ├── pvc.yaml
│   └── README.md
├── Day - 19
│   ├── pv.yaml
│   ├── pvc.yaml
│   ├── pod.yaml
│   └── README.md
├── Day - 20
│   ├── storageclass.yaml
│   ├── pvc.yaml
│   └── README.md
├── Day - 21
│   ├── daemonset.yaml
│   └── README.md
├── Day - 22
│   ├── service.yaml
│   ├── statefulset.yaml
│   └── README.md
├── Day - 23
│   ├── service.yaml
│   ├── statefulset.yaml
│   └── README.md
├── Day - 24
│   ├── job.yaml
│   └── README.md
├── Day - 25
│   ├── cronjob.yaml
│   └── README.md
├── Day - 26
│   ├── pod.yaml
│   └── README.md
├── Day - 27
│   ├── deployment.yaml
│   └── README.md
├── Day - 28
│   ├── deployment.yaml
│   └── README.md
├── Day - 29
│   ├── pod.yaml
│   └── README.md
└── Day - 30
    ├── namespace.yaml
    ├── configmap.yaml
    ├── secret.yaml
    ├── pvc.yaml
    ├── deployment.yaml
    ├── service.yaml
    └── README.md
```

Every folder contains:

- Kubernetes manifest(s)
- Minimal README
- Commands to deploy and verify
- Key concepts learned

---

# 🧩 Topics Covered

## Core Workloads

- ✅ Pod
- ✅ Multi-Container Pod
- ✅ Namespace
- ✅ ReplicaSet
- ✅ Deployment
- ✅ Rolling Updates
- ✅ Rollbacks
- ✅ DaemonSet
- ✅ StatefulSet

---

## Networking

- ✅ ClusterIP Service
- ✅ NodePort Service
- ✅ LoadBalancer Service
- ✅ Headless Service
- ✅ Service Load Balancing

---

## Configuration

- ✅ ConfigMap
- ✅ Secret

---

## Storage

- ✅ emptyDir
- ✅ hostPath
- ✅ PersistentVolume (PV)
- ✅ PersistentVolumeClaim (PVC)
- ✅ StorageClass

---

## Batch Workloads

- ✅ Job
- ✅ CronJob

---

## Reliability

- ✅ Resource Requests
- ✅ Resource Limits
- ✅ Liveness Probe
- ✅ Readiness Probe
- ✅ Startup Probe
- ✅ Init Containers

---

## Production Deployment

The final project combines multiple Kubernetes resources into a production-style application, including:

- Namespace
- ConfigMap
- Secret
- PersistentVolumeClaim
- Deployment
- Service
- Resource Requests & Limits
- Health Probes

---

# 🛠️ Prerequisites

- Kubernetes Cluster (Minikube, Kind, K3s, Docker Desktop, EKS, AKS, or GKE)
- kubectl
- Basic understanding of YAML

Verify your cluster:

```bash
kubectl cluster-info
kubectl get nodes
```

---

# ▶️ How to Use

Clone the repository:

```bash
git clone https://github.com/sriramch163/Kubernetes-Manifest-30-Day-Challenge.git
```

Go into any day's folder:

```bash
cd "Day - 10"
```

Deploy the manifests:

```bash
kubectl apply -f .
```

Verify the resources:

```bash
kubectl get all
```

Clean up:

```bash
kubectl delete -f .
```

---

# 🎓 Skills Gained

After completing this challenge, you'll have hands-on experience with:

- Writing Kubernetes YAML manifests
- Managing Pods and Deployments
- Kubernetes networking
- Storage management
- Application configuration
- Health checks
- Stateful applications
- Batch processing
- Production deployment patterns

---

# 📖 References

- Kubernetes Official Documentation
- Kubernetes API Reference
- kubectl Documentation

---

# 🤝 Contributions

Suggestions, improvements, and feedback are always welcome.

If you find this repository helpful, consider giving it a ⭐.

---

# 👨‍💻 Author

**Sriram Chandika**

- GitHub: https://github.com/sriramch163

---

## ⭐ If this repository helped you learn Kubernetes, consider starring it!
