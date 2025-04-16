Absolutely! Here’s a **detailed technical Kafka CLI cheatsheet**, covering essential and advanced `kafka-*` command-line tools provided with Kafka. This includes syntax, options, examples, and explanations, ideal for developers and administrators working in a **Java/Kafka context**.

---

# 🧾 **Kafka CLI Cheatsheet**

> **Note:** Assumes you're in the Kafka `bin/` directory or have it added to your `PATH`.

---

## 🔧 **Setup and Environment**

| Command | Description |
|--------|-------------|
| `kafka-server-start.sh config/server.properties` | Start Kafka broker using config file. |
| `kafka-server-stop.sh` | Stop the Kafka server. |
| `zookeeper-server-start.sh config/zookeeper.properties` | Start ZooKeeper instance. |
| `zookeeper-server-stop.sh` | Stop ZooKeeper. |

---

## 📁 **Topic Management**

### ▶️ Create a Topic

```bash
kafka-topics.sh --create \
  --bootstrap-server localhost:9092 \
  --replication-factor 1 \
  --partitions 3 \
  --topic my-topic
```

### 📋 List Topics

```bash
kafka-topics.sh --list --bootstrap-server localhost:9092
```

### ℹ️ Describe a Topic

```bash
kafka-topics.sh --describe \
  --bootstrap-server localhost:9092 \
  --topic my-topic
```

### ❌ Delete a Topic

```bash
kafka-topics.sh --delete \
  --bootstrap-server localhost:9092 \
  --topic my-topic
```

---

## 📤 **Producing Messages**

```bash
kafka-console-producer.sh \
  --broker-list localhost:9092 \
  --topic my-topic
```

🔹**Options:**
- `--property "parse.key=true"`  
- `--property "key.separator=:"`  
  → Send key-value messages like `key1:value1`.

### Example with Keyed Messages:

```bash
kafka-console-producer.sh \
  --broker-list localhost:9092 \
  --topic keyed-topic \
  --property "parse.key=true" \
  --property "key.separator=:"
```

---

## 📥 **Consuming Messages**

```bash
kafka-console-consumer.sh \
  --bootstrap-server localhost:9092 \
  --topic my-topic \
  --from-beginning
```

🔹**Common Flags:**
- `--group my-group` → Assign to a consumer group.
- `--offsets` → Display offset info.
- `--property print.key=true`  
- `--property key.separator=:`  
- `--timeout-ms 10000` → Stop after 10 seconds.

---

## ⛳ **Offset Management**

### View Offsets for a Consumer Group

```bash
kafka-consumer-groups.sh \
  --bootstrap-server localhost:9092 \
  --group my-group \
  --describe
```

### List All Consumer Groups

```bash
kafka-consumer-groups.sh --bootstrap-server localhost:9092 --list
```

### Reset Offsets

```bash
kafka-consumer-groups.sh \
  --bootstrap-server localhost:9092 \
  --group my-group \
  --topic my-topic \
  --reset-offsets \
  --to-earliest \
  --execute
```

🔹Other Offset Reset Options:
- `--to-latest`  
- `--to-offset <n>`  
- `--shift-by <+n|-n>`  
- `--by-duration <PT10M>`  
- `--to-datetime <timestamp>`

---

## 🛠️ **Kafka Admin Tasks**

### Create a New Partition

```bash
kafka-topics.sh \
  --bootstrap-server localhost:9092 \
  --alter \
  --topic my-topic \
  --partitions 6
```

### Add Config to a Topic

```bash
kafka-configs.sh \
  --bootstrap-server localhost:9092 \
  --entity-type topics \
  --entity-name my-topic \
  --alter \
  --add-config retention.ms=60000
```

---

## 🧪 **Testing and Debugging**

### Produce Test Data to a Topic

```bash
seq 10 | kafka-console-producer.sh \
  --broker-list localhost:9092 \
  --topic test-topic
```

### Consume with Timestamp

```bash
kafka-console-consumer.sh \
  --bootstrap-server localhost:9092 \
  --topic test-topic \
  --property print.timestamp=true \
  --from-beginning
```

---

## 🗃️ **Kafka Logs Tool**

### Dump Segment Files (useful for debugging)

```bash
kafka-run-class.sh kafka.tools.DumpLogSegments \
  --files /tmp/kafka-logs/my-topic-0/00000000000000000000.log \
  --print-data-log
```

---

## 🧩 **Kafka Connect CLI**

### Start Connect in Standalone Mode

```bash
connect-standalone.sh \
  config/connect-standalone.properties \
  config/source.properties \
  config/sink.properties
```

### Start in Distributed Mode

```bash
connect-distributed.sh config/connect-distributed.properties
```

---

## 🔒 **Security Related CLI**

### Create ACLs

```bash
kafka-acls.sh \
  --bootstrap-server localhost:9092 \
  --add \
  --allow-principal User:alice \
  --operation Read \
  --topic my-topic
```

### List ACLs

```bash
kafka-acls.sh \
  --bootstrap-server localhost:9092 \
  --list
```

---

## 🗂️ **Other Useful Commands**

### View Cluster Info

```bash
kafka-broker-api-versions.sh --bootstrap-server localhost:9092
```

### Run Java Class (for custom Java tools)

```bash
kafka-run-class.sh com.mycompany.MyKafkaTool
```

---

## 📚 Tip: Helpful Config Files

| File | Purpose |
|------|---------|
| `server.properties` | Kafka broker config |
| `zookeeper.properties` | ZooKeeper config |
| `consumer.properties` | CLI consumer config |
| `producer.properties` | CLI producer config |
| `connect-standalone.properties` | Connect worker config |
| `connect-distributed.properties` | Connect distributed config |

---

Would you like this cheatsheet as a downloadable PDF, or maybe versioned by Kafka release (like 2.8 vs 3.x)?
