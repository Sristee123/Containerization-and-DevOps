# 🚀 Class Task

---

## 🛠️ Tools Used  
- Docker  
- k3d  
- kubectl  
- Kubernetes  

---

## ⚙️ Steps  

### Check k3d Commands  
```bash
k3d
k3d cluster
```

---

### List Existing Clusters  
```bash
k3d cluster list
```

---

### Start Cluster  
```bash
k3d cluster start mycluster
```

---

### Verify Cluster Again  
```bash
k3d cluster list
```

---

### Check Pods (Initial State)  
```bash
kubectl get pods
```

---

### Create Pod  
```bash
kubectl run nginx --image=nginx
```

---

### Describe Pod  
```bash
kubectl describe pod nginx
```

---

### Check Pod Logs  
```bash
kubectl logs nginx
```

---

### Create Deployment  
```bash
kubectl create deployment web --image=nginx
```

---

### Scale Deployment  
```bash
kubectl scale deployment web --replicas=3
```

---

### Expose Deployment  
```bash
kubectl expose deployment web --port=80 --type=NodePort
```

---

### Check Services  
```bash
kubectl get services
```

---

### Check Pods  
```bash
kubectl get pods
```

---

### Delete Pod  
```bash
kubectl delete pod nginx
```

---

## ⚠️ Notes  
- Initially no pods were present in default namespace  
- A single nginx pod was created and verified  
- Deployment created multiple replicas (3 pods)  
- NodePort service exposes the application externally  
- Typo in command (`sclae`) corrected to `scale` 😅  

---

## ✅ Outcome  
- Kubernetes cluster successfully managed using k3d  
- Pod creation, logs, and inspection verified  
- Deployment scaled to multiple replicas  
- Service exposed using NodePort  
- Pod deletion tested successfully  

---

## 📸 Screenshots  

> Add your screenshots here:

![Screenshot 1](./Images/Screenshot%202026-03-19%20103829.png)
![Screenshot 2](./Images/Screenshot%202026-03-19%20103841.png)
![Screenshot 3](./Images/Screenshot%202026-03-19%20103901.png)
![Screenshot 4](./Images/Screenshot%202026-03-19%20105608.png)