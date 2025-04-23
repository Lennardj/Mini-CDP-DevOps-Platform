# Mini-CDP-DevOps-Platform
Build a simplified Customer Data Platform environment that ingests mock customer data, transforms it, and exposes it via an API for marketing applications—deployed on a cloud environment with full CI/CD, container orchestration, and security compliance.

# System Architecture
+----------------------+
|     GitHub Repo      |
|----------------------|
| - App Code (FastAPI) |
| - Terraform Scripts  |
| - K8s Manifests      |
+----------+-----------+
           |
           v
+-------------------------------+
|       GitHub Actions CI/CD   |
|-------------------------------|
| - Run Tests & Linting        |
| - Build Docker Image         |
| - Push to Docker Hub         |
| - Deploy to K8s Cluster      |
+-------------------------------+
           |
           v
+-------------------------------+
|      Kubernetes Cluster       |
|-------------------------------|
| +-------------------------+  |
| |  FastAPI Microservice   |  |
| |  (Pods + Service)       |  |
| +-------------------------+  |
|                             |
| +-------------------------+ |
| |  PostgreSQL Database     | |
| |  (StatefulSet + PVC)     | |
| +-------------------------+ |
|                             |
| +-------------------------+ |
| |  CronJob: Data Ingestion | |
| +-------------------------+ |
+-------------------------------+
           |
           v
+-----------+-----------+-----------+
|                       |           |
v                       v           v
+------------------+  +----------+  +------------------------+
|   Prometheus     |  | Grafana  |  | AWS Secrets Manager    |
| - Scrape metrics |  | - Dashboards | - API keys & DB creds |
+------------------+  +----------+  +------------------------+

