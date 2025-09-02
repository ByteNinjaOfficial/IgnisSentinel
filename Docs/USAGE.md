# 📄 USAGE.md

Once running, you can interact with IgnisSentinel via **web dashboard**.

---

## 🔹 Web Dashboard

* URL → [http://localhost:8000/web](http://localhost:8000/web)
* Features:

  * Add/remove cameras
  * View live streams with detections
  * Logs & gallery browsing
  * Snapshots with filters

---

## 🔹 Telegram Bot

* Start chat with your bot
* Authenticate with the password from `.env`
* Commands:

  * `/start` → subscribe to alerts
  * `/stop` → unsubscribe

Alerts include **snapshot + timestamp**.

---

## 🔹 API Endpoints

* `/` → API root
* `/health` → service status
* `/cameras` → list/add cameras
* `/logs/combined` → all logs
* `/gallery/images` → snapshots

WebSocket streaming → `/video/{camera_name}`

---

## 🔹 Logs & Snapshots

* Stored in `Program/logs/`
* Auto-created on first run
* Includes both detections and Telegram bot logs

---