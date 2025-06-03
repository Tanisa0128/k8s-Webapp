# K8s-webapp

 This project contains Kubernetes configuration files to deploy a web application and its MongoDB backend.

## Project Files

 - `mongo.yaml` — Deployment and Service for MongoDB  
 - `webapp.yaml` — Deployment and NodePort Service for the web application  
 - `Configmap.yaml` — ConfigMap for application environment variables (e.g., DB URL)  
 - `mongo-secret.yaml` — Secret for sensitive data  (e.g., DB Username and Password)

---

## Prerequisites

 - Kubernetes cluster running (Docker Desktop Kubernetes or Minikube recommended)  
 - kubectl command-line tool configured to communicate with your cluster

---

## How to Deploy

 ```bash
 kubectl apply -f configmap.yaml
 kubectl apply -f secret.yaml
 kubectl apply -f mongo.yaml
 kubectl apply -f webapp.yaml

---

## Verify pod and service is running

 ```bash
 kubectl get pods
 kubectl get svc

---

## Check Pod IP Address

 ```bash
 kubectl get pods -o wide

---

## Troubleshooting 
   
 ```bash
 kubectl logs <pod-name>
 kubectl describe pod <pod-name>

---

## Accessing the Web Application

 - If using **Docker Desktop**, open: `http://localhost:<NodePort>`
 - If using **Minikube**, open: `http://<Minikube_IP>:<NodePort>`

 > Replace `<NodePort>` with the value defined in `webapp.yaml` (e.g., 30100).





