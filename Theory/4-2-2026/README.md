# 🐳 Docker Daemon Configuration & TCP Access – Class Task

---

## 🛠️ Technologies Used  
- Docker  
- WSL (Windows Subsystem for Linux)  
- Linux Commands  

---

## ⚙️ Steps Performed  

### 1️⃣ Edit Docker Daemon Configuration  
```bash
sudo nano /etc/docker/daemon.json
```

### Updated Configuration:
```json
{
  "hosts": [
    "unix:///var/run/docker.sock",
    "tcp://0.0.0.0:2375"
  ]
}
```

---

### 2️⃣ Reload Docker Configuration  
```bash
sudo systemctl daemon-reexec
```

---

### 3️⃣ Restart Docker Service  
```bash
sudo systemctl restart docker
```

---

### 4️⃣ Check Docker Service Status  
```bash
sudo service docker status
```

---

### 5️⃣ Stop and Start Docker Service  
```bash
sudo service docker stop
sudo service docker start
```

---

### 6️⃣ Kill and Restart Docker Daemon (Manual)  
```bash
sudo pkill dockerd
sudo dockerd &
```

---

### 7️⃣ Verify Docker Command  
```bash
docker
```

---

### 8️⃣ Check Port Binding (2375)  
```bash
ss -lntp | grep 2375
```

---

## ⚠️ Notes  
- Docker daemon was configured to listen on both:
  - Unix socket  
  - TCP port `2375`  
- Port `2375` allows remote API access (insecure if not protected)  
- Restarting Docker is required after configuration changes  
- Manual daemon restart can be used for troubleshooting  

---

## ✅ Outcome  
- Successfully modified Docker daemon configuration  
- Enabled TCP access for Docker API  
- Restarted and verified Docker service  
- Confirmed port binding for external communication  

---

## 📸 Screenshots  

> all screenshots below:

![Screenshot 1](./Images/Screenshot%202026-02-04%20112956.png)
![Screenshot 2](./Images/Screenshot%202026-02-04%20113151.png)
![Screenshot 3](./Images/Screenshot%202026-02-04%20114709.png)
![Screenshot 4](./Images/Screenshot%202026-02-04%20115454.png)
![Screenshot 5](./Images/Screenshot%202026-02-04%20115502.png)