# 🚀 AWS Kubernetes GitOps — Déploiement d'une application Node.js

## 📌 Présentation

Ce projet personnel consiste à déployer et superviser une application **Node.js sur un cluster Kubernetes hébergé sur AWS**, en utilisant une approche GitOps.

L'objectif est de mettre en pratique les concepts de **Cloud Computing, Infrastructure as Code (IaC), Kubernetes, GitOps et Observabilité**.

## 🏗️ Architecture

![Architecture du projet](docs/architecture.png)

## 🛠️ Technologies utilisées

| Technologie | Rôle |
|---|---|
| AWS CloudFormation | Provisionnement de l'infrastructure |
| AWS EC2 / VPC | Hébergement et réseau |
| Kubernetes (kubeadm) | Orchestration des conteneurs |
| Argo CD | Déploiement GitOps |
| Prometheus | Collecte des métriques |
| Grafana | Visualisation et monitoring |
| GitHub | Gestion des manifestes Kubernetes |

## ⚙️ Fonctionnement

**1. Infrastructure AWS**

CloudFormation provisionne un VPC (`10.0.0.0/16`), un subnet public et deux instances EC2 Ubuntu 22.04 (Control Plane et Worker).

**2. Déploiement Kubernetes**

L'application Node.js est déployée avec :
- Un `Deployment` configuré avec **2 réplicas**.
- Un `Service` Kubernetes.

**3. GitOps avec Argo CD**

Argo CD synchronise les manifestes Kubernetes stockés dans GitHub avec le cluster.

**4. Monitoring**

Prometheus collecte les métriques Kubernetes, visualisées dans Grafana.

## 📸 Démonstration

### Argo CD — Applications Healthy / Synced

![Argo CD](docs/argocd-tab.png)

### Grafana — Monitoring des Pods

![Grafana](docs/tableau-grafana.png)

### Kubernetes — État des ressources

![Kubernetes](docs/kubernetes-terminal.png)

## 📂 Structure du dépôt

```text
my-app-gitops/
├── README.md
├── cloudformation/
│   └── infrastructure.yaml
├── deployment.yaml
├── docs/
│   ├── architecture.png
│   ├── argocd-tab.png
│   ├── kubernetes-terminal.png
│   └── tableau-grafana.png
├── k8s/
└── service.yaml
```

## 🔮 Améliorations prévues

- Ajouter un Ingress Controller et HTTPS.
- Configurer un Horizontal Pod Autoscaler (HPA).
- Ajouter des readiness et liveness probes.
- Renforcer la sécurité Kubernetes.
- Étendre les fonctionnalités de l'application Node.js.

---

**Projet personnel — Cloud / DevOps / Kubernetes**

*Cheikh Fallou Wade*
