# 🐳 Class Task

---

## 🛠️ Tools Used  
- Docker  
- Nginx  
- Ubuntu  
- Alpine Linux  

---

## ⚙️ Steps  

### Create Dockerfile (Ubuntu Base)  
```dockerfile
FROM ubuntu:22.04

RUN apt-get update && \
    apt-get install -y nginx && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
```

---

### Create Dockerfile (Alpine Base)  
```dockerfile
FROM alpine:latest

RUN apk add --no-cache nginx

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
```

---

### Create HTML File  
```html
<h1>Hello from Docker NGINX</h1>
```

---

### Build Docker Image  
```bash
docker build -t nginx-app .
```

---

### Run Container  
```bash
docker run -d -p 8080:80 nginx-app
```

---

### Access Application  
Open browser:  
```
http://localhost:8080
```

---

## ⚠️ Notes  
- Ubuntu image is larger but more familiar  
- Alpine image is lightweight and faster  
- Nginx runs in foreground using `daemon off;`  
- Port 80 inside container mapped to 8080 on host  

---

## ✅ Outcome  
- Created Docker images using two base images  
- Deployed Nginx container  
- Served custom HTML page  
- Compared Ubuntu vs Alpine images  

---

## 📸 Screenshots  


![Screenshot 1](./Images/Screenshot%202026-02-19%20225554.png)
![Screenshot 2](./Images/Screenshot%202026-02-19%20225932.png)
![Screenshot 3](./Images/Screenshot%202026-02-19%20230159.png)
