# 📄 TROUBLESHOOTING.md

## 🔹 Common Issues

**❌ Dashboard not loading**

* Check if container is running: `docker ps`
* Verify port `8000` is available

**❌ No video feed**

* Ensure `cameras.json` has valid sources
* For USB: add `--device /dev/video0` to Docker run
* Test RTSP/IP streams externally (VLC, ffmpeg)

**❌ Model not found**

* Place `best.pt` in `Program/model/`


**❌ No Telegram alerts**

* Verify `TELEGRAM_API_KEY` and authorized users
* Check `Program/logs/telegram_bot.log`

**❌ Slow performance**

* Lower `INFERENCE_SIZE` or `MAX_FPS` in `.env`
* Use GPU if available

**❌ GPU not detected**

* Install NVIDIA Container Toolkit
* Run with `--gpus all`

---

## 🔹 Debugging

* Logs → `docker logs ignissentinel`
* Health check → [http://localhost:8000/health](http://localhost:8000/health)
* Restart → `docker compose restart`

---
