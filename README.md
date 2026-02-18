<h1 align="center">Grafana</h1>

>Previously, we configured Prometheus along with Node Exporter to collect infrastructure and application metrics.
>Prometheus is responsible for data collection (Pull Model).
>
>Now, we will explore Grafana, which is used for data visualization.
>
>👉 Prometheus = Data Collection
>👉 Grafana = Data Visualization (Dashboards)

---

- [About Grafana](#example-0)
- [Conclusion- Quick Flow](#example-1)
- [Grafana Monitoring Setup](#example-2)







---

<p align="center">
  <img src="" width="500" alt="Initialize Repository Screenshot">
</p>


<a id="example-0"></a>




##  1️⃣ Grafana

>You can also see about grafana in their offical docmuntation[click here](https://grafana.com/docs/grafana/latest/introduction/)

Grafana is an open-source analytics and interactive visualization platform used to query, visualize, and analyze monitoring data from multiple data sources such as Prometheus, CloudWatch, MySQL, Elasticsearch, and others.

Grafana does not collect metrics by itself.<br>
It connects to external data sources and converts raw time-series data into meaningful dashboards and graphs.

Grafana is widely used in cloud-native and production environments as the visualization layer of the observability stack.

---

###  Key facts

- **Initial release**: 2014
- **Developer**: Grafana Labs
- **Primary language**: Go and TypeScript
- **License**: Apache License 2.0
- **Primary purpose**: Data visualization and dashboarding

---

###  Architecture and operation

Grafana works by connecting to configured data sources.

Instead of storing metrics like Prometheus, Grafana:

1. Connects to a data source (e.g., Prometheus)
2. Queries data using the source’s query language (PromQL for Prometheus)
3. Displays results in dashboards
4. Allows alert creation based on queries

Grafana does not follow a pull or push model for data collection.<br>
It only visualizes data that has already been collected and stored.

---

###  Ecosystem and integrations

Grafana supports multiple data sources including:<br>

- Prometheus
- Amazon CloudWatch
- Azure Monitor
- Google Cloud Monitoring
- MySQL
- PostgreSQL
- Elasticsearch
- InfluxDB

Grafana is commonly used with:<br>

- Prometheus (metrics collection)
- Alertmanager (alert routing)
- Loki (log monitoring)
- Tempo (distributed tracing)

Grafana acts as the visualization layer in modern observability systems.

---

###  Importance in observability

Grafana is important because monitoring data without visualization is difficult to interpret.<br>
It transforms raw metrics into interactive dashboards, helping engineers understand system health in real time.

It enables teams to:

- Detect performance issues
- Track trends over time
- Analyze spikes and anomalies
- Make data-driven decisions

Grafana plays a key role in monitoring microservices, infrastructure, and applications across industries.

---

##  2️⃣ Grafana vs Prometheus

###  🔹 Prometheus

- Open-source monitoring tool
- Collects and stores metrics
- Uses Pull model
- Requires exporters
- Uses PromQL
- Handles alert generation

###  🔹 Grafana

- Open-source visualization tool
- Does not collect metrics
- Connects to data sources
- Displays dashboards
- Supports alerting based on queries

👉 Prometheus = Data Collection + Storage<br>
👉 Grafana = Data Visualization

Example:<br>
Prometheus stores CPU usage data.<br>
Grafana displays CPU usage in a real-time graph.

---

##  3️⃣ Types of Visualization in Grafana

Grafana provides multiple panel types:<br>

- Time-series graphs
- Bar charts
- Pie charts
- Tables
- Stat panels
- Gauge panels
- Heatmaps

Visualization answers:<br>
👉 What is happening right now?<br>
👉 How has performance changed over time?<br>
👉 Are there unusual spikes?

---

##  4️⃣ How Grafana Works (Architecture)

Grafana does not collect data directly.

Grafana works as a visualization layer that connects to an external monitoring system like Prometheus.

---

###  Flow:

```
Application /Server → Node Exporter → Prometheus → Grafana → Dashboard
```
---

###  Step-by-step:

1. Prometheus collects metrics from exporters and applications.
2. Prometheus stores those metrics in its time-series database.
3. Grafana connects to Prometheus as a data source.
4. Grafana queries metrics using PromQL.
5. The results are displayed in dashboards as graphs and panels.

---

Grafana acts as the frontend layer of monitoring.<br>
Prometheus handles data collection and storage, while Grafana handles visualization.



---

## 5️⃣ Configuration (Imp)

Grafana requires proper configuration to function correctly.

Inside Grafana, you configure:<br>

- Data Sources (e.g., Prometheus URL)
- Dashboard panels
- Queries (PromQL when using Prometheus)
- Alert rules

Example concept:

If Prometheus runs on port 9090:

```
http://localhost:9090
```

So Grafana mainly depends on:<br>
👉 Correct data source configuration<br>
👉 Proper query writing<br>
👉 Logical dashboard design

If data source is wrong → No data visible<br>
If query is wrong → Panel shows error

The real skill in Grafana is:

Understanding how to connect data sources<br>
Writing correct queries<br>
Designing meaningful dashboards

---

##  6️⃣ What is the Main Job of Grafana?

Grafana does not collect data.<br>
Grafana does not fix problems.

Its job is:<br>
✔ Visualize metrics<br>
✔ Create dashboards<br>
✔ Display trends<br>
✔ Trigger alerts<br>
✔ Help analyze system behavior

In simple words:<br>

>Grafana shows monitoring data in a clean, visual, and understandable format.

Prometheus stores numbers(data).<br>
Grafana turns those numbers into graphs.

---

##  7️⃣ Advantages

✔ Open-source<br>
✔ Multi-cloud support<br>
✔ Supports multiple data sources<br>
✔ Professional dashboards<br>
✔ Alerting support<br>
✔ Highly customizable<br>
✔ Strong community ecosystem

---

##  8️⃣ Limitations

❌ Does not collect metrics<br>
❌ Requires external data source<br>
❌ Needs proper configuration knowledge<br>
❌ Complex dashboards require query understanding

---

<a id="example-1"></a>

##  ✅ Conclusion

Grafana is primarily a visualization tool whose core purpose is:

>To convert collected monitoring data into interactive dashboards for better visibility and analysis.

It does not collect metrics.<br>
It does not store time-series data by default.<br>
It simply:<br>

- Connects to data sources<br>
- Queries metrics<br>
- Displays dashboards<br>
- Helps analyze performance

---

Grafana is an open-source visualization platform that transforms monitoring data into meaningful dashboards.<br>
Its primary purpose is to provide visibility into system and application behavior through visual representation.

To use Grafana effectively, one must understand how to configure data sources, write proper queries, and design dashboards logically.

---

###  🎯 In Simple Words

Whatever metrics you collect:<br>

- CPU<br>
- Memory<br>
- Disk<br>
- Application requests<br>
- Errors<br>
- Kubernetes metrics<br>

Grafana visualizes them — if it is properly connected to a data source.

---

###  🔹 The Most Important Skill in Grafana

The main thing you must understand is:

✔ How to connect Prometheus properly<br>
✔ How to write correct PromQL queries<br>
✔ How to design dashboards logically<br>
✔ How to configure alerts

Because Grafana works only if:

- Data source is correctly configured
- Queries are correct
- Dashboards are properly designed

If configuration is wrong → No visualization<br>
If query is wrong → No graph

So yes, the real skill in Grafana is:

>Understanding visualization and configuration.



---
---
---
---



<br>
<br>



<a id="example-2"></a>


##  📊 Grafana Monitoring Setup

###  📌 Important Note Before Starting

Previously, we launched an EC2 instance for Prometheus and Node Exporter.

For this setup, we will use the same instance and simply open port **3000** in the Security Group for Grafana.

In real-time production environments:

- Prometheus server can be on a separate instance
- Grafana server can be on a different instance
- Node Exporter can run on multiple different servers

It is not mandatory that everything runs on the same machine.

However, instead of launching three different instances, we are using a single instance for simplicity and cost optimization.

Difference:

- If everything runs on the same server → we use `localhost:PORT`
- If running on different servers → we must use Private IP or Public IP addresses

One more reason for using a single instance:

👉 It simplifies networking and avoids unnecessary security group configuration complexity during learning.

In production, separation improves scalability and security.
In learning, simplicity improves understanding.

---

##  1️⃣ Update Security Group

Add the following inbound rule:

| Port | Purpose |
|------|----------|
| 3000 | Grafana |

Source:
```
0.0.0.0/0
```

Why:

Grafana runs on port 3000 by default.  
Without opening this port, the dashboard will not be accessible from the browser.

---

##  2️⃣ Connect to Server

Use SSH:

```bash
ssh -i your-key.pem ubuntu@your-public-ip
```

---

##  3️⃣ Change Hostname (Optional but Recommended)

To clearly identify this server as a monitoring server:

```bash
sudo hostnamectl set-hostname monitoring-server
```

Why:

Changing hostname improves clarity when managing multiple servers.

---

##  4️⃣ Install Grafana (Using Official APT Repository)

⚠ Always refer to official documentation:

https://grafana.com/docs/grafana/latest/setup-grafana/installation/debian/

Reason:

Installation steps, repository URLs, and syntax may change over time.  
Following official documentation ensures correct and secure installation.

---

### Step 1: Install Prerequisite Packages

```bash
sudo apt-get install -y apt-transport-https wget gnupg
```

Why:

Required to securely download and verify packages from external repositories.

---

### Step 2: Import Grafana GPG Key

```bash
sudo mkdir -p /etc/apt/keyrings/
wget -q -O - https://apt.grafana.com/gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/grafana.gpg > /dev/null
```

Why:

This ensures package authenticity and prevents installation of tampered packages.

---

### Step 3: Add Grafana Repository (Stable Release)

```bash
echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```

Why:

Adds Grafana’s official repository to your system.

(Stable release is recommended for production usage.)

---

### Step 4: Update Package List

```bash
sudo apt-get update
```

Why:

Refreshes available packages from newly added repository.

---

### Step 5: Install Grafana OSS

```bash
sudo apt-get install grafana
```

Why:

Installs the latest stable Grafana Open Source version.

---

##  5️⃣ Start and Enable Grafana Service

```bash
sudo systemctl daemon-reload
sudo systemctl start grafana-server
sudo systemctl enable grafana-server
sudo systemctl status grafana-server
```

Why:

- Start → Runs Grafana immediately
- Enable → Starts automatically after reboot
- Status → Confirms service is active

---

##  6️⃣ Access Grafana Dashboard

Open in browser:

```
http://YOUR_PUBLIC_IP:3000
```

Default credentials:

```
Username: admin
Password: admin
```

You will be prompted to change the password after first login.

---

###  🔍 Important Understanding

Since Prometheus is running on the same server:

In Grafana Data Source configuration, we use:

```
http://localhost:9090
```

If Prometheus were on a different server:

We would use:

```
http://PRIVATE_IP:9090
```
or
```
http://PUBLIC_IP:9090
```

So networking configuration depends on deployment architecture.

---

##  ✅ Overview

For learning:

Single server → Simple networking → localhost usage

For production:

Separate servers → Better scalability and isolation → IP-based communication

Grafana is now successfully installed and ready to connect with Prometheus.


---












































































































