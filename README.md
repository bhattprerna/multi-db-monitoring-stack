# 📊 Multi-Database Monitoring Stack with Prometheus & Grafana

This project sets up a full monitoring stack using Docker Compose for:

- 🐬 **MySQL Master-Slave Replication**
- 🍃 **MongoDB Replica Set (Primary-Secondary-Secondary)**
- 🧠 **Redis Server**
- 📈 **Prometheus and Grafana** for real-time observability
- 📡 **Node Exporter**, **MySQL Exporter**, **MongoDB Exporter**, and **Redis Exporter**

---

## 🔧 Tech Stack

| Component        | Description                     |
|------------------|---------------------------------|
| `mysql-master`   | Primary MySQL node              |
| `mysql-slave`    | Replicating slave node          |
| `mongo1/2/3`     | MongoDB replica set             |
| `redis`          | In-memory key-value store       |
| `prometheus`     | Metrics scraping + storage      |
| `grafana`        | Metrics visualization           |
| `node-exporter`  | System-level metrics            |
| `mysqld-exporter`| MySQL metrics                   |
| `mongodb-exporter`| MongoDB metrics                |
| `redis-exporter` | Redis metrics                   |

---

---

## 🚀 Getting Started

### 1. Clone the repository
git clone https://github.com/bhattprerna/multi-db-monitoring-stack.git
cd multi-db-monitoring-stack

**2. Launch the full stack:**
docker compose up -d

3. Access the services:
📊 Grafana → http://localhost:3000
Default credentials: admin / admin

🔍 Prometheus → http://localhost:9090

📊 Metrics Monitored

✅ MySQL (via mysqld-exporter)
Replication lag

Uptime

Threads & connections

Queries per second

✅ MongoDB (via mongodb-exporter)
Replica set state

Memory and connections

Operations & cursors

✅ Redis (via redis-exporter)
Memory usage

Keyspace hits/misses

Clients

CPU

✅ Host (via node-exporter)
CPU

Memory

Disk

System uptime

Network I/O

🛠 MongoDB Replica Set Initialization

After starting containers, initialize the replica set from mongo1:
rs.initiate({
  _id: "rs0",
  members: [
    { _id: 0, host: "mongo1:27017" },
    { _id: 1, host: "mongo2:27017" },
    { _id: 2, host: "mongo3:27017" }
  ]
})

📸 Dashboard Previews

🧑‍💻 Author
Prerna Bhatt
💼 DevOps Enthusiast
🔗 LinkedIn
📦 GitHub
