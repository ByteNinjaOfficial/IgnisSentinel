# 🔥 IgnisSentinel – AI-Powered Fire & Smoke Detection

IgnisSentinel is an **AI-powered fire and smoke detection system** using YOLO for **real-time analysis of video streams**.
It provides:

* 🖥️ **Web dashboard** for monitoring live feeds & detections
* 📱 **Telegram alerts** with snapshots
* 🎥 **Support for USB, IP, and RTSP cameras**
* ⚡ **GPU acceleration (CUDA)** with automatic CPU fallback
* 🐳 **Lightweight Docker deployment**

---

## ✨ Features

* 🚨 Detects **fire & smoke in real time**
* 🌐 Web UI with logs, gallery, and live camera feeds
* 🤖 Telegram bot for instant notifications
* 🎥 Multi-camera support (USB, RTSP, IP streams)
* 🔧 Configurable via external files (`.env`, `cameras.json`, `authorized_users.json`)
* 📦 Portable & reproducible with Docker
* 💾 Persistent logs and snapshots via bind-mounted volumes

---

## 📦 Quick Start

### 1. Pull the Docker Image

* **For NVIDIA GPU (CUDA Accelerated):**
  ```bash
  docker pull byteninja16/ignissentinel:latest
  ```
* **For CPU (Lightweight, No GPU required):**
  ```bash
  docker pull byteninja16/ignissentinel:cpu
  ```

### 2. Prepare Project Directory & Volumes

```bash
main/
├── Program/
│   ├── config/
│   │   └── .env            # Telegram bot API key & dashboard password
│   ├── data/               # Persistent SQLite WAL database (cameras, history)
│   ├── logs/               # Persistent system logs & threat snapshots
│   │   └── detected_fire/
│   └── model/
│       └── best.pt         # Your trained YOLOv11 model weights
```

### 3. Run with Docker Compose

* **Run with GPU (Default):**
  ```bash
  docker compose up -d
  ```
* **Run with CPU:**
  ```bash
  docker compose -f docker-compose.cpu.yml up -d
  ```

* Enterprise Dashboard → [http://localhost:8080](http://localhost:8080)
* Health Check → [http://localhost:8080/health](http://localhost:8080/health)


---

## 🚀 Usage

* Open [http://localhost:8000/web](http://localhost:8000/web) → login with `.env` password.
* Manage cameras, view detections, check logs & gallery.
* Telegram bot will send alerts to authorized users with snapshots.

---

## ⚡ GPU vs CPU

* If GPU is available → auto uses CUDA.
* If not → falls back to CPU.

Run with GPU:

```bash
docker run --gpus all ...
```

Run CPU-only:

```bash
docker run --gpus=none ...
```

---

## 📚 Documentation

* [Installation Guide](Docs/INSTALLATION.md)
* [Configuration Reference](Docs/CONFIGURATION.md)
* [Usage Guide](Docs/USAGE.md)
* [Troubleshooting](Docs/TROUBLESHOOTING.md)

---

## 📜 License

This project is licensed under the **Apache License, Version 2.0**.
See the [LICENSE](LICENSE) file for full details.

---

## 🙌 Contributing

Contributions are welcome!

* Report bugs via [Issues](../../issues).
* Suggest features or improvements.
* Submit PRs for enhancements.

---

## 📸 Example Use Cases

* 🔥 Fire monitoring in server rooms
* 🏭 Industrial smoke detection in factories
* 🏠 Smart home safety
* 🏢 Office compliance monitoring

---