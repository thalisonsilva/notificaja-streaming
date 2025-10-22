# 🌀 NotificaJá Streaming

**Real-time event processor for the NotificaJá ecosystem**, built with Go and Apache Kafka.  
This service is responsible for consuming notification events and triggering actions (e.g., email delivery) based on message content.

----

## 📌 What is this?

This is the **streaming/worker service** of the [NotificaJá](https://github.com/thalison/notificaja-api) project.  
It listens to Kafka topics and processes notification events in real time.

The goal is to create a scalable and production-ready streaming layer using modern, high-performance technologies.

---

## 🧪 Tech Stack

| Layer                 | Technology             |
|-----------------------|------------------------|
| Language              | Go (Golang)            |
| Event Streaming       | Apache Kafka           |
| Email Sending         | SMTP (Gomail or Mailgun integration) |
| Configuration         | Environment variables (.env or YAML) |
| Logging (future)      | Zerolog or Logrus      |
| Monitoring (future)   | Prometheus + Grafana   |
| Containerization (future) | Docker + Compose |

----

## 🧱 Project Structure

```
notificaja-streaming/
├── cmd/                    # Application entrypoint
│   └── main.go
├── internal/
│   ├── kafka/              # Kafka consumer logic
│   ├── processor/          # Notification logic (email, etc)
│   └── handlers/           # Event handlers by type
├── configs/                # Config files or .env
├── go.mod
└── README.md
```

---

## 🚀 How to Run (Development Mode)

1. Clone the repository:

```bash
git clone https://github.com/thalison/notificaja-streaming.git
cd notificaja-streaming
```

2. Install dependencies:

```bash
go mod tidy
```

3. Run the project:

```bash
go run cmd/main.go
```

> **Note:** You need a running Apache Kafka instance.  
> Use Docker or connect to a cluster (e.g., Confluent Cloud) and configure the broker address in `.env`.

---

## 📡 Kafka Topics (example)

| Topic Name       | Description                  |
|------------------|------------------------------|
| `notifications`  | Main topic for notification events |
| `errors`         | (Future) Dead-letter topic for failures |

---

## 🛠️ Features (WIP)

- [x] Project structure
- [ ] Kafka consumer initialization
- [ ] Email notification handler
- [ ] Logging and error handling
- [ ] Retry mechanism for failed messages
- [ ] Metrics with Prometheus

---

## 🤝 Contributing

This project is part of an open learning journey.  
Feel free to fork, open issues, or suggest improvements.

---

## 📄 License

MIT — free to use, modify, and learn from.

---

## 👨‍💻 Author

**Thalison Moreira da Silva**  
Building from scratch. Learning in public. Streaming with purpose.
