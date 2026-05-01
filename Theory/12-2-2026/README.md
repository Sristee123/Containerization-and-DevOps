# 🐳 Class Task

---

## 🛠️ Tools Used  
- Docker  
- Nginx  
- WSL  

---

## ⚙️ Steps  

### Run Nginx Container with Bind Mount  
```bash
docker run -d \
--name nginx-container \
--mount type=bind,source=/home/sristee/html,target=/usr/share/nginx/html \
-p 8080:80 \
nginx
```

---

### Remove Container (Incorrect Command Attempt)  
```bash
docker rm -f nginx container
```

**Error:**  
- No such container: nginx  
- No such container: container  

---

### Remove Container (Correct Command)  
```bash
docker rm -f nginx-container
```

---

### Run Container with tmpfs Mount  
```bash
docker run -d \
--name temp-container \
--mount type=tmpfs,target=/app/cache \
nginx
```

---

## ⚠️ Notes  
- Bind mount links host directory to container (`/home/sristee/html`)  
- Incorrect container name caused removal error  
- `tmpfs` mount stores data in memory (non-persistent)  
- Data in `tmpfs` is lost when container stops  

---

## ✅ Outcome  
- Successfully used bind mount with Nginx  
- Understood container naming importance  
- Implemented `tmpfs` mount  
- Learned difference between persistent and non-persistent storage  

---

## 📸 Screenshots  
![Screenshot 1](./Images/Screenshot%202026-02-12%20103910.png)