# 🐳 DOCKER – Class Task

---

## 🛠️ Technologies Used  
- Docker  
- WSL (Windows Subsystem for Linux)  
- Linux Commands  

---

## ⚙️ Steps Performed  

### 1️⃣ Stop Docker Service  
```bash
sudo service docker stop
```

---

### 2️⃣ Start Docker Service  
```bash
sudo service docker start
```

---

### 3️⃣ Kill Running Docker Daemon  
```bash
sudo pkill dockerd
```

---

### 4️⃣ Attempt Manual Start of Docker Daemon  
```bash
sudo dockerd &
```

---

### 5️⃣ Check Port Usage  
```bash
ss -lntp | grep 2375
```

---

## ❌ Issue Encountered  

While starting Docker daemon manually, the following error occurred:

```
failed to start daemon, ensure docker is not running or delete /var/run/docker.pid: process with PID XXXX is still running
```

---

## 🔍 Cause  
- Docker daemon was already running in the background  
- Existing PID file (`/var/run/docker.pid`) prevented a new instance from starting  

---

## 🛠️ Resolution  

### Option 1: Remove PID File  
```bash
sudo rm /var/run/docker.pid
```

### Option 2: Ensure No Running Docker Process  
```bash
ps aux | grep dockerd
```

Kill if needed:
```bash
sudo kill -9 <PID>
```

---

### Restart Docker Properly  
```bash
sudo systemctl restart docker
```

---

## ⚠️ Notes  
- Only one Docker daemon instance can run at a time  
- Manual `dockerd` start may conflict with system service  
- Always check running processes before restarting  

---

## ✅ Outcome  
- Identified Docker daemon conflict issue  
- Understood PID file role in process management  
- Applied troubleshooting steps to resolve daemon startup failure  

---

## 📸 Screenshots  

>screenshots below:

![Screenshot 1](./Images/Screenshot%202026-02-05%20105049.png)