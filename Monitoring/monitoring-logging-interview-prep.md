# Monitoring & Logging Interview Preparation  
## Prometheus, Grafana, ELK – Casebook Style 📊📈

This document is designed for **DevOps interviews**, focusing on **monitoring and logging**
questions commonly asked in real-world interviews and production troubleshooting.

Each topic explains:
- 📌 What it is
- 🧠 Why it matters in production
- ⚠️ Common mistakes
- 🛠️ Real interview scenarios & debugging steps

---

# PART 1: Monitoring Fundamentals

## 1. What is monitoring and why is it important?

📌 **Answer:**  
Monitoring is the process of collecting, visualizing, and alerting on system and application metrics.

🧠 **Why it matters:**  
Monitoring helps detect issues before users are impacted and ensures system reliability.

⚠️ **Mistake:**  
Monitoring only infrastructure and ignoring application metrics.

---

## 2. What is the difference between monitoring and logging?

📌 **Answer:**  
- Monitoring → Metrics (CPU, memory, latency)
- Logging → Events and detailed records

🧠 **Interview Tip:**  
Both are required for effective troubleshooting.

---

# PART 2: Prometheus – Metrics & Alerting

## 3. What is Prometheus?

📌 **Answer:**  
Prometheus is an open-source monitoring system that collects metrics using a pull-based model.

🧠 **Why it matters:**  
Widely used with Kubernetes for metrics collection.

---

## 4. How does Prometheus collect metrics?

📌 **Answer:**  
Prometheus scrapes metrics from HTTP endpoints exposed by applications or exporters.

⚠️ **Mistake:**  
Forgetting to expose `/metrics` endpoint.

---

## 5. What is an exporter in Prometheus?

📌 **Answer:**  
An exporter exposes metrics from systems like Linux, databases, or applications.

🛠️ **Examples:**  
Node Exporter, Blackbox Exporter

---

## 6. What is PromQL?

📌 **Answer:**  
PromQL is Prometheus Query Language used to query metrics.

🧠 **Why it matters:**  
Used for dashboards and alerting.

---

## 7. Prometheus alerts are not firing. What do you check?

🛠️ **Steps:**
- Check alert rules syntax
- Verify metric availability
- Check Alertmanager configuration

---

# PART 3: Grafana – Visualization

## 8. What is Grafana?

📌 **Answer:**  
Grafana is a visualization tool used to build dashboards from data sources like Prometheus.

🧠 **Why it matters:**  
Makes metrics human-readable.

---

## 9. How does Grafana integrate with Prometheus?

📌 **Answer:**  
Grafana queries Prometheus using PromQL and displays metrics in dashboards.

---

## 10. Dashboard shows no data. How do you debug?

📌 **Answer:**  
- Check data source connection
- Validate PromQL queries
- Check time range

---

# PART 4: Logging – ELK Stack

## 11. What is the ELK Stack?

📌 **Answer:**  
ELK stands for Elasticsearch, Logstash, and Kibana.

🧠 **Why it matters:**  
Centralized logging and log search.

---

## 12. Role of each ELK component

📌 **Answer:**  
- Elasticsearch → Storage & search
- Logstash → Log processing
- Kibana → Visualization

---

## 13. What is Beats?

📌 **Answer:**  
Lightweight agents used to ship logs.

🛠️ **Examples:**  
Filebeat, Metricbeat

---

## 14. Logs are missing in Kibana. How do you debug?

🛠️ **Steps:**
- Check Beats agent
- Verify Logstash pipeline
- Check Elasticsearch indices

---

# PART 5: Real Interview Scenarios

## 15. Application is slow. How do you use monitoring to debug?

📌 **Answer:**  
- Check latency metrics
- Check CPU/memory usage
- Correlate with logs

---

## 16. Too many alerts are firing. What do you do?

📌 **Answer:**  
- Review alert thresholds
- Remove noisy alerts
- Use alert grouping

---

## 17. Node is down but no alert triggered. Why?

📌 **Answer:**  
- Exporter not running
- Alert rule misconfigured
- Alertmanager issue

---

## 18. How do you design a monitoring strategy?

📌 **Answer:**  
- Monitor RED/USE metrics
- Define SLIs and SLOs
- Alert on symptoms, not causes

---

## 19. Metrics show spike but logs look fine. What next?

📌 **Answer:**  
- Check downstream dependencies
- Check network latency
- Check database performance

---

## 20. How do you secure monitoring and logging systems?

📌 **Answer:**  
- RBAC
- TLS encryption
- Authentication
- Limit access to dashboards

---

📌 **Final Interview Tip:**  
Interviewers expect you to explain monitoring in terms of **reliability, alert quality, and user impact**.
