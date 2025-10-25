# 🚀 Locust Performance Monitoring

A lightweight setup for performance testing with **Locust**, visualized in **Grafana**, and monitored by **Prometheus** via the **Locust Exporter**.

---

## 📦 What's Inside
- **Locust** – load testing  
- **Locust Exporter** – exposes Locust metrics  
- **Prometheus** – scrapes and stores metrics  
- **Grafana** – dashboards + alerts  

---

## 🏗️ Quick Start

### 1️⃣ Clone the project
```bash
git clone https://github.com/IbekweVictor/locust-performance-monitoring.git
cd locust-monitoring
````

### 2️⃣ Start everything

```bash
docker compose up -d
```

### 3️⃣ Open the dashboards

* **Locust UI:** [http://localhost:8089](http://localhost:8089)
* **Prometheus:** [http://localhost:9090](http://localhost:9090)
* **Grafana:** [http://localhost:3000](http://localhost:3000)
  *(Login: admin / admin)*

---

## ⚙️ Email Alerts

Grafana alerts can send notifications by email.
Before starting containers, edit your **docker-compose.yml**:

```yaml
GF_SMTP_USER: "youremail@example.com"
GF_SMTP_PASSWORD: "your_app_password"
```

> ⚠️ Use your **app password**, not your normal email password.

---

## 📊 Key Metrics Visualized

| Metric                              | Description                                |
| ----------------------------------- | ------------------------------------------ |
| `locust_running`                    | Test status (Stopped / Hatching / Running) |
| `locust_users`                      | Active users                               |
| `locust_requests_current_rps`       | Requests per second                        |
| `locust_requests_avg_response_time` | Average response time                      |
| `locust_requests_fail_ratio`        | Failure percentage                         |
| `locust_errors`                     | Error breakdown                            |

---

## 🧠 Folder Layout

```
.
├── docker-compose.yml
├── grafana/
│   ├── dashboards/
│   │   └── locust-dashboard.json
│   └── provisioning/
│       ├── datasources/
│       └── dashboards/
├── prometheus/
│   └── prometheus.yml
└── locust/
    ├── locustfile.py
    └── requirements.txt
```

---

## 📜 License

MIT © 2025

---

Made with ❤️ for performance engineers.

