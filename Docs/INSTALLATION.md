# 📄 INSTALLATION.md

## 🔹 Prerequisites

* [Docker](https://docs.docker.com/get-docker/) (latest version)
* [Docker Compose](https://docs.docker.com/compose/)
* Optional: **NVIDIA GPU** with drivers + [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)

---

## 🔹 Setup Steps

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/IgnisSentinel.git
cd IgnisSentinel
```

### 2. Pull the Docker Image

```bash
docker pull byteninja16/ignissentinel
```

### 3. Create Directory Structure

```bash
main/
├── Program/
│   ├── config/
│   │   ├── .env
│   │   ├── cameras.json
│   │   └── authorized_users.json
│   ├── logs/
│   └── model/
│       └── best.pt
```

### 4. Run with Docker Compose

```bash
docker compose up -d
```

* Web Dashboard → [http://localhost:8000/web](http://localhost:8000/web)
* API Root → [http://localhost:8000](http://localhost:8000)

---

## 🔹 GPU vs CPU

* **GPU mode** → requires NVIDIA Container Toolkit

  ```bash
  docker run --gpus all ...
  ```

* **CPU-only** → remove GPU settings in `docker-compose.yml` or run with:

  ```bash
  docker run --gpus=none ...
  ```

---