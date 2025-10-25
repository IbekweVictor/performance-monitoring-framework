# Locust Performance Monitoring Stack

A complete performance testing and monitoring setup using **Locust**, **Prometheus**, **Grafana**, and the **Locust Exporter**.

## 🧩 Stack Overview
- **Locust** – load testing tool  
- **Locust Exporter** – exposes Locust metrics to Prometheus  
- **Prometheus** – collects and stores metrics  
- **Grafana** – visualizes metrics and alerts  

## 📁 Project Structure
```

.
├── docker-compose.yml
├── grafana/
│   ├── dashboards/
│   │   └── locust-dashboard.json
│   └── provisioning/
│       ├── dashboards/
│       └── datasources/
├── prometheus/
│   └── prometheus.yml
└── locust/
├── locustfile.py
└── requirements.txt

````

## 🚀 Setup Instructions
1. **Clone the repository**
   ```bash
   git clone https://github.com/IbekweVictor/locust-performance-monitoring.git
   cd locust-performance-monitoring
````

2. **Start the stack**

   ```bash
   docker-compose up -d
   ```

3. **Access the services**

   * **Locust UI:** [http://localhost:8089](http://localhost:8089)
   * **Prometheus:** [http://localhost:9090](http://localhost:9090)
   * **Grafana:** [http://localhost:3000](http://localhost:3000)

     * *Default login:* `admin / admin`

4. **Import the Grafana dashboard**

   * Navigate to **Dashboards → Import**
   * Upload `grafana/dashboards/locust-dashboard.json`

## ⚠️ Email Alert Configuration

Grafana alerts are sent via email.
Before running Docker Compose, edit `docker-compose.yml` and update:

```yaml
GF_SMTP_USER: "your_email@example.com"
GF_SMTP_PASSWORD: "your_app_password"
```

> ⚠️ Use your **email app password**, not your regular email password.

## 🧠 Metrics Tracked

* **locust_running** – test status (Stopped / Hatching / Running)
* **locust_users** – active users
* **locust_requests_current_rps** – requests per second
* **locust_requests_avg_response_time** – average response time
* **locust_requests_num_failures** – total failures
* **locust_requests_fail_ratio** – failure percentage
* **locust_errors** – error breakdown by type

## 🧾 License

MIT License © 2025

---

### 🌐 Repository Summary

End-to-end Locust performance testing and monitoring stack with Prometheus, Grafana, and alerting support.

