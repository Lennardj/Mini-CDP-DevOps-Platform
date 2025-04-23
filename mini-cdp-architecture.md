
# 📐 Mini-CDP DevOps Platform – System Architecture

```
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
```

## 🗃️ Suggested Folder Structure

```
mini-cdp-devops/
├── app/                  # FastAPI code
├── db/                   # SQL schema or mock data
├── docker/               # Dockerfiles
├── k8s/                  # Kubernetes manifests
├── terraform/            # Infrastructure-as-Code
├── .github/workflows/    # GitHub Actions pipelines
├── README.md             # Project overview & architecture
```
