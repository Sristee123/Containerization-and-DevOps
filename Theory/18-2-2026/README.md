# 🐳 Class Task

---

## 🛠️ Tools Used  
- Docker  
- WSL  
- Nginx  
- BusyBox  

---

## ⚙️ Steps  

### List Docker Networks  
```bash
docker network ls
```

---

### Inspect Default Bridge Network  
```bash
docker network inspect bridge
```

---

### Create Custom Bridge Network  
```bash
docker network create my_bridge
```

---

### Inspect Custom Network  
```bash
docker network inspect my_bridge
```

---

### Run First Container (Nginx) on Custom Network  
```bash
docker run -dit --name container1 --network my_bridge nginx
```

---

### Run Second Container (BusyBox) on Same Network  
```bash
docker run -dit --name container2 --network my_bridge busybox
```

---

### Test Connectivity Between Containers  
```bash
docker exec -it container2 ping container1
```

---

### Run Container Using Host Network  
```bash
docker run -d --network host nginx
```

---

### Verify Port Binding  
```bash
ss -lntp | grep 80
```

---

## ⚠️ Notes  
- Default `bridge` network is automatically created by Docker  
- Custom bridge network allows container-to-container communication using names  
- `ping container1` worked due to internal DNS resolution  
- Host network mode shares host’s networking stack  
- Port `80` was directly exposed on host without mapping  

---

## ✅ Outcome  
- Explored Docker network types  
- Created and inspected custom bridge network  
- Verified container communication using ping  
- Understood difference between bridge and host networking  

---

## 📸 Screenshots  

![Screenshot 1](./Images/Screenshot%202026-02-18%20114838.png)
![Screenshot 2](./Images/Screenshot%202026-02-18%20114848.png)
![Screenshot 3](./Images/Screenshot%202026-02-18%20114857.png)
![Screenshot 4](./Images/Screenshot%202026-02-18%20115145.png)