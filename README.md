
---

# Kafka + Spark Streaming Project

Project ini mendemonstrasikan implementasi event streaming menggunakan Apache Kafka, pemrosesan data dengan Apache Spark, serta eksplorasi melalui Jupyter Notebook dalam lingkungan tercontainerisasi menggunakan Docker.

---

## Project Structure

```
.
├── docker-compose.yaml
├── README.md
├── report.docx
└── scripts
    ├── producer.ipynb
    ├── consumer1.ipynb
    ├── consumer2.ipynb
    └── consumer3.ipynb
```
---
## Execution Steps
### 1. Start Services

Pastikan Docker dan Docker Compose telah terinstall, kemudian jalankan:

```bash
docker-compose up -d
```

Service yang akan berjalan:

* Jupyter Notebook + Spark
* Kafka Broker
* Kafka UI

---

### 2. Access Jupyter Notebook

Buka browser dan akses:

```
http://localhost:8888
```

Masuk ke folder `scripts/`, kemudian jalankan:

* `producer.ipynb`
* `consumer1.ipynb`
* `consumer2.ipynb`
* `consumer3.ipynb`

---

### 3. Access Kafka UI

Buka browser dan akses:

```
http://localhost:8080
```

Gunakan Kafka UI untuk:

* Memantau topic
* Melihat partition
* Mengamati consumer group

---

### 4. Create Topic (If Not Exists)

Jika topic belum tersedia, jalankan:

```bash
docker exec -it kafka kafka-topics \
  --bootstrap-server localhost:9092 \
  --create \
  --topic events_topic \
  --partitions 3 \
  --replication-factor 1
```

---

### 5. Stop Services

Untuk menghentikan seluruh service:

```bash
docker-compose down
```

Untuk menghapus volume:

```bash
docker-compose down -v
```

---
