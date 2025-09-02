# 📄 CONFIGURATION.md

All configurations live in **`Program/config/`** and are provided via bind mounts.

---

## 🔹 Environment Variables (`.env`)

Structure:

```ini
TELEGRAM_API_KEY = "YOUR_TELEGRAM_API_KEY"  # Your bot's API token (provided by @BotFather) 

PASSWORD = "YOUR_PASSWORD"  # The password required for user authentication

```

---

## 🔹 Cameras (`cameras.json`)

Cameras can be configured either manually or conveniently through the web dashboard; manual setup is optional.

```json
[
  { "id": "webcam", "source": 0 },
  { "id": "warehouse", "source": "rtsp://user:pass@192.168.1.100:554/stream" }
]
```

* `source: 0` → USB webcam
* `source: URL` → RTSP/IP camera

---

## 🔹 Authorized Users (`authorized_users.json`)

This file stores the Telegram user IDs used for sending alerts. Manual editing is not required unless you wish to add or remove users yourself. The program manages this file automatically—when a user enters the correct bot password, their user ID is updated here.

```json
{
  [123456789, 987654321]
}
```

---

## 🔹 Model (`best.pt`)

* Place your YOLO model inside `Program/model/`.

* Note: You can download and use the pre-trained model provided in the GitHub repository, or alternatively, you may use a custom model of your own.
* If using a custom model, ensure it is renamed to `best.pt` to maintain compatibility with the system.
---