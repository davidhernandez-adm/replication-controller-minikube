# 📦 Kubernetes ReplicationController (Minikube)

A focused project demonstrating how to create and manage **ReplicationControllers** in Kubernetes using **Minikube**. It includes two YAML configurations to showcase how ReplicationControllers ensure pod availability and consistency.

---

## 📌 Project Overview

* **Name**: replication-controller-minikube
* **Stack**: Kubernetes YAML, Minikube
* **Goal**: Demonstrate the use of `ReplicationController` to maintain a stable set of pod replicas
* **Use Case**: Educational resource for legacy Kubernetes workload controllers

---

## 📁 Project Structure

```
├── rc.yaml       # ReplicationController creating 2 nginx pods with label `project: nginx`
├── rc2.yaml      # Second ReplicationController using a different label `project: nginx2`
```

---

## 🚀 Getting Started

### Prerequisites

* [Minikube](https://minikube.sigs.k8s.io/docs/start/)
* [kubectl](https://kubernetes.io/docs/tasks/tools/)

### Installation Steps

```bash
# 1. Start Minikube
minikube start

# 2. Apply the ReplicationControllers
kubectl apply -f rc.yaml
kubectl apply -f rc2.yaml

# 3. Check created pods
kubectl get pods

# 4. Observe how deletion triggers automatic replacement
kubectl delete pod <pod-name>
kubectl get pods
```

---

## 📦 Technologies Used

* **Kubernetes** – For orchestration and scaling
* **Minikube** – Local Kubernetes cluster
* **YAML** – Declarative resource management

---

## 🧪 Testing and Coverage

> Not applicable. Manual validation is done by observing pod recreation after deletion.

### Example:

```bash
kubectl get rc
kubectl describe rc nginx
```

---

## 🧠 Key Challenges & Learnings

* Reinforced the mechanics of **ReplicationController**, an early Kubernetes controller
* Compared behavior with **ReplicaSets** for legacy understanding
* Practiced label-based pod management using `selector`

---

## 📷 Screenshots or Live Demo

> CLI Output Example:

```bash
kubectl get rc
NAME      DESIRED   CURRENT   READY   AGE
nginx     2         2         2       10s
nginx2    2         2         2       8s
```

---

## 📜 License

[MIT](https://opensource.org/licenses/MIT)

---

> Built by [David Hernández](https://github.com/davidhernandez-adm) as part of Kubernetes fundamentals training and practice.
