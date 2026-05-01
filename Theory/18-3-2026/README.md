# 🐳 Class Task

---

## 🛠️ Tools Used  
- Docker  
- k3d  
- kubectl  
- WSL  

---

## ⚙️ Steps  

### Download kubectl (Initial Attempt)  
```bash
curl -LO https://dl.k8s.io/release/stable/bin/linux/amd64/kubectl
```

---

### Fix Download Using Correct Version  
```bash
VERSION=$(curl -L -s https://dl.k8s.io/release/stable.txt)

curl -LO https://dl.k8s.io/release/$VERSION/bin/linux/amd64/kubectl
```

---

### Make kubectl Executable  
```bash
chmod +x kubectl
sudo mv kubectl /usr/local/bin/
```

---

### Verify kubectl Installation  
```bash
kubectl version --client
```

---

### Install k3d  
```bash
curl -s https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh | bash
```

---

### Verify k3d Installation  
```bash
k3d version
```

---

### Create Kubernetes Cluster  
```bash
k3d cluster create mycluster
```

---

### Check Cluster Nodes  
```bash
kubectl get nodes
```

---

### Check Context  
```bash
kubectl config get-contexts
```

---

## ⚠️ Notes  
- Initial kubectl download failed due to incorrect URL  
- Correct version fetched dynamically using `stable.txt`  
- k3d creates lightweight Kubernetes cluster using Docker  
- kubectl is used to interact with the cluster  

---

## ✅ Outcome  
- Installed kubectl successfully  
- Installed k3d and created cluster  
- Verified cluster node status  
- Confirmed Kubernetes context configuration  

---

## 📸 Screenshots  

![Screenshot 1](./Images/Screenshot%202026-03-18%20115135.png)
![Screenshot 2](./Images/Screenshot%202026-03-18%20115150.png)