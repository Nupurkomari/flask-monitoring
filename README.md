# 🚀 Flask Monitoring with Prometheus, Grafana & Slack Alerts

## 📌 Overview
This project demonstrates **end-to-end monitoring of a Flask application running on Kubernetes (Minikube)**.  
It integrates **Prometheus** for metrics collection, **Grafana** for visualization, and **Slack** for real-time alerts — enabling proactive monitoring and rapid incident response.  

---

## 🏗️ Architecture
- **Kubernetes / Minikube** → Local cluster environment  
- **Flask Application** → Custom Python app exposing a `/metrics` endpoint using the Prometheus Python client  
- **Prometheus** → Scrapes metrics from Flask app and Kubernetes components  
- **Grafana** → Interactive dashboards & alert management  
- **Slack** → Instant notifications for threshold breaches (e.g., high CPU usage, memory spikes)  

---

## ⚙️ Setup

### 1️⃣ Start Minikube
```bash
minikube start --memory=4096 --cpus=2
```

### 2️⃣ Install kube-prometheus-stack (Helm)
```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
helm install prometheus prometheus-community/kube-prometheus-stack -f values.yaml
```
> Ensure your `values.yaml` contains the **Slack webhook URL** for alerting.  

### 3️⃣ Deploy Flask App
```bash
kubectl apply -f flask-deployment.yaml
kubectl apply -f flask-service.yaml
```

### 4️⃣ Access Grafana
```bash
minikube service prometheus-grafana -n default
```
- Default login → `admin / prom-operator`  

### 5️⃣ Configure Dashboards & Alerts
- Import Prometheus dashboards in Grafana  
- Set up alert rules (e.g., CPU > 80%, Memory > 75%)  
- Link Slack as a **notification channel**  

---

## 🔔 Alerting
- Alerts trigger when **thresholds are breached** (e.g., high CPU, memory, or pod restarts).  
- Notifications are **instantly sent to Slack** for faster response.  

---

## 📊 Usage
- **Monitor metrics** → View app & cluster performance in Grafana  
- **Stay notified** → Receive Slack alerts for anomalies  
- **Proactive troubleshooting** → Quickly identify and resolve issues before they escalate  

---

## 📷 Screenshots 
- Grafana dashboard for Flask app
![](image.png)
![Grafana dashboard for Flask app](image-1.png)
- Prometheus metrics endpoint 
![alt text](image-2.png) 
- Slack alert notification
![alt text](image-3.png)

---

## ✅ Key Benefits
- End-to-end **observability** for Flask on Kubernetes  
- Automated **real-time alerting** with Slack integration  
- Production-ready monitoring setup  


