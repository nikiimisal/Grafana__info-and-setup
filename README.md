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
```
echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com beta main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
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
---

---

# 🔗 Connecting Grafana to Prometheus (Data Source Configuration)

Prometheus installation is completed.

Now we want to visualize the collected metrics.

Prometheus is already collecting data from Node Exporter and storing it.

But Grafana does not automatically know where that data is.

So we need to create a data connection.

---

## 📌 Why Data Connection is Required?

Data is already given to Prometheus.

Now Grafana must fetch that data from Prometheus.

Without connecting Grafana to Prometheus, dashboards will not show any metrics.

So the first step is:

👉 Add Prometheus as a Data Source in Grafana.

---

## 🔌 Understanding Data Sources 

Grafana supports multiple types of data sources.

You can connect:

- Prometheus
- MySQL
- PostgreSQL
- AWS RDS
- Custom Database Server
- Application metrics
- Cloud monitoring tools

In Jenkins → we call it Plugins.  
In Grafana → we call it Data Source / Connection.

Concept is similar.

If you want Prometheus data → select Prometheus connection.  
If you want MySQL data → select MySQL connection.
If you want any other monitoring tool → choose that plugin

---

## 🛠 Steps to Connect Prometheus

### 1️⃣ Open Grafana

```
http://YOUR_PUBLIC_IP:3000
```

Login with your credentials.

---

### 2️⃣ Add New Connection

1. Go to **Home**
2. Click on **Connections**
3. Click **Add new connection**
4. Select **Prometheus**
5. Add New Data Source

---

### 3️⃣ Configure URL

Currently:

Prometheus and Grafana are running on the same server.

So use:

```
http://localhost:9090
```

If Prometheus was on a different server:

```
http://PRIVATE_IP:9090
```
or
```
http://PUBLIC_IP:9090
```

For beginner understanding, keep everything on the same server.

---

### 4️⃣ Save & Test

Click:

```
Save & Test
```

If successful, you will see:

```
Data source is working
```

Now Grafana is successfully connected to Prometheus.

---

# 📊 Creating Dashboard & Viewing Data

After connecting data source:

1. Click **Dashboards**
2. Click **Create Dashboard**
3. Click **Add Visualization**
4. Select **Prometheus**

Add metric example:

```
node_cpu_seconds_total
```

Click **Run Queries**

Now you can visualize data.

---

## 📈 Visualization Formats

You can display data in different formats:

- Time Series
- Stat
- Bar Chart
- Gauge
- Table

Example:

CPU Usage → Time Series  
Single value metric → Stat  
Comparison metrics → Bar Chart  

Grafana gives flexibility to view the same data in multiple formats.

---

## ✅ Overview

Prometheus → Collects & Stores Data  
Grafana → Fetches & Visualizes Data  

Prometheus = Backend Monitoring Engine  
Grafana = Frontend Visualization Layer  

Now your monitoring stack is fully connected 🎯



---
---
---



---

# 🗄 Connecting MySQL Database to Grafana (Second Data Source Example)

Previously, we connected Prometheus as a data source.

Now let’s see another example — MySQL database connection.

Data can come from anywhere:

- Prometheus
- RDS (AWS Managed Database)
- DynamoDB
- Self-hosted database server
- Application database

There are mainly two common ways to create a database:

1️⃣ Use Managed Service (Example: AWS RDS)  
2️⃣ Install Database on Your Own Server (Self-hosted)

For learning purposes, we will:

👉 Install MySQL on the same server  
👉 Create a database and table  
👉 Connect it to Grafana  
👉 Visualize data in Dashboard  

---

## 📌 Important Networking Note

Before connecting MySQL to Grafana:

Open port **3306** in EC2 Security Group.

| Port | Purpose |
|------|----------|
| 3306 | MySQL Database |

If MySQL is on same server → technically localhost works  
But opening port is useful for testing and future remote access.

In production:
- If using RDS → we use RDS Endpoint
- If using separate DB server → use Private IP

Since everything is on the same server:

We will use:

```
localhost:3306
```

---

# 🛠 Step 1: Install MySQL (Already Completed)

You installed:

```bash
sudo apt install mysql-server -y
```

Start and Enable:

```bash
sudo systemctl start mysql
sudo systemctl enable mysql
```

---

# 🛠 Step 2: Create Database & Table

Login:

```bash
sudo mysql
```

Set root password:

```sql
alter user root@localhost identified by 'root';
```

Create database:

```sql
create database nikii;
```

Select database:

```sql
use nikii;
```

Create table:

```sql
create table student (
  id int,
  name varchar(20),
  marks int
);
```

Insert data:

```sql
insert into student values
(1, "rohan", 80),
(2, "nikii", 75);
```

Check data:

```sql
select * from student;
```

Now database is ready.

---

# 🔌 Step 3: Add MySQL as Data Source in Grafana

Open Grafana:

```
http://YOUR_PUBLIC_IP:3000
```

---

### 1️⃣ Add New Connection

- Go to **Connections**
- Click **Add new connection**
- Search for **MySQL**
- Select MySQL plugin

---

### 2️⃣ Configure MySQL Connection

Since MySQL is on same server:

Host:

```
localhost:3306
```

Database:

```
nikii
```

User:

```
root
```

Password:

```
root
```

---

### 🔎 If Database Was on RDS

Host would be:

```
your-rds-endpoint.amazonaws.com:3306
```

So difference is only networking:

Same server → localhost  
Different server → Private IP / RDS Endpoint  

---

# ⚠ Common Error You May See

Sometimes Grafana shows error like:

```
Error: This version of MySQL is not supported
```

Reason:

Grafana MySQL plugin requires a compatible MySQL version (generally MySQL 5.7+ or 8.x).

Solution:

✔ Use MySQL 8.x (recommended)  
✔ Make sure authentication plugin is compatible  

If authentication error comes, run:

```sql
ALTER USER 'root'@'localhost'
IDENTIFIED WITH mysql_native_password
BY 'root';
FLUSH PRIVILEGES;
```

Then try Save & Test again.

---

# ✅ Save & Test

Click:

```
Save & Test
```

If everything is correct:

```
Database Connection OK
```

Now MySQL is successfully connected to Grafana 🎯

---

# 📊 Step 4: Visualize MySQL Data

1. Go to **Dashboards**
2. Click **Create Dashboard**
3. Click **Add Visualization**
4. Select **MySQL**

In Query section:

```sql
SELECT * FROM student;
```

Click:

```
Run Query
```

You can now display:

- Table view
- Bar chart (marks comparison)
- Stat (highest marks)
- Time series (if using timestamp column)

---

# 🧠 Final Understanding

Prometheus → Monitoring Metrics Data  
MySQL → Structured Application Data  

Grafana can visualize:

- Monitoring data
- Database data
- Cloud data
- Application data

Grafana is not limited to Prometheus.

It is a universal visualization layer.

---

Now your monitoring + database visualization stack is complete 🚀



---
---
---


---

# 🚨 Alertmanager Setup (Prometheus Alerting System)

Prometheus collects metrics.

But monitoring is incomplete without alerting.

If CPU usage goes high  
If Memory crosses threshold  
If Server goes down  

We need automatic notifications.

For that, we use:

👉 Alertmanager

---

# 🧠 How Alerting Works

Flow:

```
Application → Prometheus → Alert Rule → Alertmanager → Email / Slack / Other Notification
```

Prometheus detects the problem.  
Alertmanager sends the notification.

Prometheus = Detection  
Alertmanager = Notification

---

# 🛠 Step 1: Download Alertmanager

Go to:
```
https://prometheus.io/download/
```
Download latest stable version.

On server:

```bash
cd /tmp
wget https://github.com/prometheus/alertmanager/releases/latest/download/alertmanager-*.linux-amd64.tar.gz
```

Extract:

```bash
tar -xvf alertmanager-*.linux-amd64.tar.gz
```

Move binaries:

```bash
sudo mv alertmanager-*/alertmanager /usr/local/bin/
sudo mv alertmanager-*/amtool /usr/local/bin/
```

---

# 🛠 Step 2: Create Alertmanager User

```bash
sudo useradd --no-create-home --shell /bin/false alertmanager
```

Create directory:

```bash
sudo mkdir /etc/alertmanager
sudo mkdir /var/lib/alertmanager
```

Set ownership:

```bash
sudo chown alertmanager:alertmanager /etc/alertmanager
sudo chown alertmanager:alertmanager /var/lib/alertmanager
```

---

# 🛠 Step 3: Create Configuration File

Create file:

```bash
sudo nano /etc/alertmanager/alertmanager.yml
```

Basic Email Example:

```yaml
global:
  smtp_smarthost: 'smtp.gmail.com:587'
  smtp_from: 'your-email@gmail.com'
  smtp_auth_username: 'your-email@gmail.com'
  smtp_auth_password: 'your-app-password'

route:
  receiver: 'email-alert'

receivers:
- name: 'email-alert'
  email_configs:
  - to: 'receiver-email@gmail.com'
```

⚠ Use App Password if using Gmail.

---

# 🛠 Step 4: Create Systemd Service

Create service file:

```bash
sudo nano /etc/systemd/system/alertmanager.service
```

Paste:

```ini
[Unit]
Description=Alertmanager
Wants=network-online.target
After=network-online.target

[Service]
User=alertmanager
ExecStart=/usr/local/bin/alertmanager \
  --config.file=/etc/alertmanager/alertmanager.yml \
  --storage.path=/var/lib/alertmanager

[Install]
WantedBy=multi-user.target
```

Reload systemd:

```bash
sudo systemctl daemon-reload
```

Start service:

```bash
sudo systemctl start alertmanager
sudo systemctl enable alertmanager
sudo systemctl status alertmanager
```

---

# 🔓 Step 5: Open Port 9093

Add Security Group rule:

| Port | Purpose |
|------|----------|
| 9093 | Alertmanager |

Access in browser:

```
http://YOUR_PUBLIC_IP:9093
```

---

# 🔗 Step 6: Connect Prometheus to Alertmanager

Edit Prometheus config:

```bash
sudo nano /etc/prometheus/prometheus.yml
```

Add:

```yaml
alerting:
  alertmanagers:
    - static_configs:
        - targets:
          - "localhost:9093"
```

Restart Prometheus:

```bash
sudo systemctl restart prometheus
```

---

# 🛠 Step 7: Create Alert Rule

Create file:

```bash
sudo nano /etc/prometheus/alert.rules.yml
```

Example CPU alert:

```yaml
groups:
- name: cpu-alerts
  rules:
  - alert: HighCPUUsage
    expr: 100 - (avg by(instance) (rate(node_cpu_seconds_total{mode="idle"}[1m])) * 100) > 80
    for: 1m
    labels:
      severity: warning
    annotations:
      summary: "High CPU Usage"
      description: "CPU usage is above 80%"
```

Now include this file in prometheus.yml:

```yaml
rule_files:
  - "/etc/prometheus/alert.rules.yml"
```

Restart Prometheus:

```bash
sudo systemctl restart prometheus
```

---

# ✅ Final Architecture

Node Exporter → Prometheus → Alert Rule → Alertmanager → Email

Now your monitoring stack includes:

✔ Metrics Collection  
✔ Visualization  
✔ Alerting System  

Production-ready monitoring foundation complete 🚀

---
---
---































































































