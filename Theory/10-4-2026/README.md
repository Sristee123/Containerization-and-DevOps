# 🚀 Class Task

---

## 🛠️ Tools Used  
- Docker  
- Portainer  

---

## ⚙️ Steps  

### Create Docker Volume  
```bash
docker volume create portainer_data
```

---

### Run Portainer Container  
```bash
docker run -d -p 8000:8000 -p 9443:9443 \
--name portainer \
--restart=always \
-v /var/run/docker.sock:/var/run/docker.sock \
-v portainer_data:/data \
portainer/portainer-ce:lts
```

---

### Verify Running Container  
```bash
docker ps
```

---

### Access Portainer  
Open in browser:  
```
https://localhost:9443
```

---

### Initial Setup  
- Create admin username & password  
- Select **Docker environment (local)**  
- Connect to Docker  

---

## ⚠️ Notes  
- Portainer image is pulled automatically if not present  
- Docker socket is mounted for container management access  
- Volume ensures persistent data storage  
- First-time setup requires creating admin credentials  
- Uses HTTPS (port 9443) for secure access 🔐  

---

## ✅ Outcome  
- Portainer container successfully deployed  
- Web UI accessed via browser  
- Docker environment connected  
- Containers, volumes, and images visible through GUI  
- Simplified Docker management using Portainer  

---

## 📸 Screenshots  

![Screenshot 1](./Images/Screenshot%202026-05-02%20005315.png)
![Screenshot 2](./Images/Screenshot%202026-05-02%20005319.png)
![Screenshot 3](./Images/Screenshot%202026-05-02%20005326.png)
![Screenshot 4](./Images/Screenshot%202026-05-02%20005354.png)
![Screenshot 5](./Images/Screenshot%202026-05-02%20005403.png)
![Screenshot 6](./Images/Screenshot%202026-05-02%20005416.png)