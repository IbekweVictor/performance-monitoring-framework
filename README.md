# 🐝 Locust Performance Monitoring Stack

A lightweight setup for monitoring **Locust load tests** using **Prometheus** and **Grafana**.  
Track performance metrics, visualize trends, and set real-time alerts — all in one place.

---

## ⚙️ Overview

**Stack Components**
- 🧠 **Locust** — Load testing tool  
- 📦 **Prometheus** — Scrapes and stores Locust metrics  
- 📊 **Grafana** — Visualizes metrics & triggers alerts  

### 🧩 Architecture

```

┌────────┐       ┌────────────┐       ┌──────────┐
│ Locust │──▶──▶│ Prometheus │──▶──▶│ Grafana  │
└────────┘       └────────────┘       └──────────┘
Load Tests     Collect Metrics     Visualize & Alert

```

---

## 📁 Project Structure

```

grafana/
├── dashboards/
│   └── locust-dashboard.json
└── provisioning/
├── dashboards.yml
└── datasource.yml
locust.py
prometheus.yml
docker-compose.yml
Dockerfile
requirements.txt

````

---

## 🚀 Quick Start

```bash
git clone https://github.com/IbekweVictor/locust-performance-monitoring.git
cd locust-performance-monitoring
docker-compose up -d
````

**Access the services:**

| Service    | URL                                            |
| ---------- | ---------------------------------------------- |
| Locust     | [http://localhost:8089](http://localhost:8089) |
| Prometheus | [http://localhost:9090](http://localhost:9090) |
| Grafana    | [http://localhost:3000](http://localhost:3000) |

---

## 📊 Dashboard Metrics

* 🧍 **Active Users (locust_users)**
* ⚙️ **Test Status (locust_running / locust_up)**
* 📈 **Requests per Second (RPS)**
* 🕒 **Avg & Median Response Time**
* 💥 **Failure Rate & Errors**

---

## 🔔 Alerts

| Condition         | Example Expression                              |
| ----------------- | ----------------------------------------------- |
| High Failure Rate | `locust_requests_fail_ratio * 100 > 10`         |
| Slow Response     | `avg(locust_requests_avg_response_time) > 1000` |
| Low Throughput    | `sum(locust_requests_current_rps) < 50`         |

---

## 🧩 Requirements

* Docker
* Docker Compose
* Python 3.9+ (optional for local Locust runs)

---

## 🧾 License

MIT License © 2025 Ibekwe Victor

