# 🚀 Class Task

---

## 🛠️ Tools Used  
- Kubernetes (kubectl)  
- k3d  
- Docker  

---

## ⚙️ Steps  

### Create Apache Pod  
```bash
kubectl run apache-pod --image=httpd
```

---

### Check Pod Status  
```bash
kubectl get pods
```

---

### Describe Pod  
```bash
kubectl describe pod apache-pod
```

---

### Port Forward Pod  
```bash
kubectl port-forward pod/apache-pod 8081:80
```

---

### Delete Pod  
```bash
kubectl delete pod apache-pod
```

---

### Create Apache Deployment  
```bash
kubectl create deployment apache --image=httpd
```

---

### Check Deployment & Pods  
```bash
kubectl get deployments
kubectl get pods
```

---

### Expose Deployment  
```bash
kubectl expose deployment apache --port=80 --type=NodePort
```

---

### Port Forward Service  
```bash
kubectl port-forward service/apache 8082:80
```

---

### Scale Deployment  
```bash
kubectl scale deployment apache --replicas=2
```

---

### Describe Pod (Replica)  
```bash
kubectl describe pod <pod-name>
```

---

### Update Image  
```bash
kubectl set image deployment/apache httpd=httpd
```

---

### Execute Inside Pod  
```bash
kubectl exec -it <pod-name> -- /bin/bash
```

---

### Delete Pod (Auto Recreation)  
```bash
kubectl delete pod <pod-name>
kubectl get pods -w
```

---

### Delete Deployment & Service  
```bash
kubectl delete deployment apache
kubectl delete service apache
```

---

## ⚠️ Notes  
- Pod initially in `ContainerCreating` / `Pending` state before running  
- Port forwarding fails if pod is not yet running  
- Service creation duplicated → “already exists” error handled  
- Deployment ensures pod auto-recreation after deletion 🔁  
- `<pod-name>` must be replaced with actual pod name (common mistake 👀)  

---

## ✅ Outcome  
- Apache pod and deployment successfully created  
- Scaling tested with multiple replicas  
- Service exposed and accessed via port forwarding  
- Pod lifecycle (create → delete → recreate) verified  
- Deployment cleanup completed successfully  

---

## 📸 Screenshots  

> 
![Screenshot 1](./Images/Screenshot%202026-03-25%20114622.png)
![Screenshot 2](./Images/Screenshot%202026-03-25%20114822.png)
![Screenshot 3](./Images/Screenshot%202026-03-25%20115510.png)
![Screenshot 4](./Images/Screenshot%202026-03-25%20115522.png)