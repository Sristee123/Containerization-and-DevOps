# 🐳 Class Task

---

## 🛠️ Tools Used  
- Docker  
- WSL  
- Ubuntu  

---

## ⚙️ Steps  

### Create a Docker Volume  
```bash
docker volume create myvolume
```

### List Volumes  
```bash
docker volume ls
```

---

### Run Container with Volume  
```bash
docker run -it --name test -v test:/home/app ubuntu /bin/bash
```

---

### Create Directory and File inside Container  
```bash
mkdir -p /home/app
cd /home/app
echo "sapid123" > sapid.txt
```

---

### Exit and Check Containers  
```bash
exit
docker ps -a
```

---

### Remove Container  
```bash
docker rm <container_id>
```

---

### Run Container Again with Volume  
```bash
docker run -it --name test2 -v test:/home/app ubuntu /bin/bash
```

---

### Verify File  
```bash
cat /home/app/sapid.txt
```

(File not found due to incorrect volume mapping)

---

### Run Container with Correct Bind Mount  
```bash
docker run -it --rm -v ./test:/home/app ubuntu /bin/bash
```

---

### Create File Again  
```bash
cd /home/app
echo test1234321 > sapid.txt
exit
```

---

### Verify from Host System  
```bash
cd test
cat sapid.txt
```

---

## ⚠️ Notes  
- Named volume (`test`) did not map as expected  
- Bind mount (`./test:/home/app`) worked correctly  
- Data persisted between container and host  

---

## ✅ Outcome  
- Created and used Docker volumes  
- Understood difference between named volume and bind mount  
- Verified data persistence  

---

## 📸 Screenshots  
![Screenshot 1](./Images/Screenshot%202026-02-11%20115755.png)
![Screenshot 2](./Images/Screenshot%202026-02-11%20115808.png)
![Screenshot 3](./Images/Screenshot%202026-02-11%20115823.png)
![Screenshot 4](./Images/Screenshot%202026-02-11%20115834.png)