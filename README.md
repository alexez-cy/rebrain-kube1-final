## About

This project was completed as the final assignment of the [Rebrain Kubernetes course](https://rebrainme.com/courses/kubernetes-base). The objective was to deploy a production-like application stack while following Kubernetes best practices, including workload deployment, persistent storage, service discovery, ingress configuration, and secure secret management.



# Kubernetes Application Deployment

Production-style Kubernetes deployment of a LibreSpeed application with a MySQL backend.

This repository demonstrates deployment of a multi-tier application using native Kubernetes manifests, including persistent storage, configuration management, secrets, networking, and ingress.

---

## Architecture

```
                    Internet
                        │
                 NGINX Ingress
                        │
                  LibreSpeed App
                        │
                 ClusterIP Service
                        │
                     MySQL
                        │
                 Persistent Volume
```

---

## Project Structure

```
.
├── app
│   ├── deployment.yaml
│   ├── ingress.yaml
│   ├── namespace.yaml
│   ├── service.yaml
│   ├── librespeed-env.yaml
│   ├── librespeed-secret.yaml
│   ├── librespeed-servers.yaml
│   └── registry-secret.yaml
│
├── db
│   ├── mysql.yaml
│   ├── mysql-service.yaml
│   ├── mysql-headless.yaml
│   ├── mysql-pvc.yaml
│   ├── mysql-configmap.yaml
│   ├── mysql-secret.yaml
│   ├── mysql-init.yaml
│   ├── mysql-secret.yaml
│   └── namespace.yaml
│
└── README.md
```

---

## Features

- Kubernetes native manifests
- Separate namespaces for application and database
- MySQL persistent storage
- ConfigMaps for application configuration
- Secrets for sensitive data
- ClusterIP services
- Headless service for database discovery
- NGINX Ingress
- Environment variable configuration
- Docker registry authentication

---

## Kubernetes Resources

### Application

- Namespace
- Deployment
- Service
- Ingress
- ConfigMap
- Secret
- Registry Secret

### Database

- Namespace
- Deployment
- ClusterIP Service
- Headless Service
- PersistentVolumeClaim
- ConfigMap
- Secret
- Initialization ConfigMap

---

## Deployment

Create namespaces

```bash
kubectl apply -f app/namespace.yaml
kubectl apply -f db/namespace.yaml
```

Deploy MySQL

```bash
kubectl apply -f db/
```

Deploy the application

```bash
kubectl apply -f app/
```

Verify resources

```bash
kubectl get pods -A
kubectl get svc -A
kubectl get ingress -A
kubectl get pvc -A
```

---

## Technologies

- Kubernetes
- Docker
- MySQL
- LibreSpeed
- NGINX Ingress
- Persistent Volumes
- ConfigMaps
- Secrets

---

## Skills Demonstrated

- Kubernetes application deployment
- Multi-tier architecture
- Stateful workloads
- Persistent storage
- Service discovery
- Ingress configuration
- Secret management
- Configuration management
- Networking
- Linux container administration

---
