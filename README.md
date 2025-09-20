Flask Monitoring Project with Prometheus, Grafana & Slack Alerts
Overview
This project demonstrates how to monitor a Flask application running on Kubernetes (Minikube) using Prometheus and Grafana with real-time alert notifications sent via Slack.

Architecture
Kubernetes / Minikube: Local cluster environment

Prometheus: To scrape metrics from the Flask app and cluster components

Grafana: Visual dashboards and alert management

Slack: Receive instant alerts for threshold breaches like high CPU usage

Flask: Custom app exposing Prometheus metrics endpoint

Setup
Deploy Minikube Kubernetes cluster.

Install kube-prometheus-stack Helm chart with custom values for Slack webhook URL.

Deploy Flask app with Prometheus Python client instrumentation.

Configure Grafana dashboards and alert rules.

Link Slack notifications for alerts.

Alerting
Alerts trigger when CPU usage or other critical metrics breach thresholds.

Notifications sent to Slack channel for rapid incident awareness.

Usage
Monitor app and system metrics via Grafana.

Receive alerts in Slack for proactive issue handling.

Screenshots
