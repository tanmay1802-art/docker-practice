# docker-practice
Docker practice on Ubuntu VirtualBox - containers, networking, macvlan setup
# 🐳 Docker Practice on Ubuntu

## 📌 Description
This is my personal Docker practice log. I explored Docker installation, 
container management, port mapping, and macvlan network configuration 
on Ubuntu running inside VirtualBox.

---

## 🛠️ What I Practiced

### 1. Install Docker
```bash
sudo apt install docker.io  -y
```

### 2. Run Containers
```bash
sudo docker run -itd --name stormbraker nginx
sudo docker run -itd --name mjolnir busybox sh
sudo docker run -itd --name thor busybox sh
```

### 3. Check Running Containers
```bash
sudo docker ps
```

### 4. Stop a Container
```bash
sudo docker stop stormbraker
```

### 5. Run Container with Port Mapping
```bash
sudo docker run -itd --rm -p 80:80 --name stormbraker nginx
```

### 6. Check IP Address
```bash
ip address show
```

### 7. Create Macvlan Network
```bash
sudo docker network create -d macvlan \
  --subnet 10.0.2.0/24 \
  --gateway 10.0.2.1 \
  -o parent=enp0s3 \
  newasgard 
```

### 8. Inspect Bridge
'''bash
sudo docker inspect bridge
--- 

## 📸 Screenshots!


---

## 📝 What I Learned
- How to install Docker on Ubuntu
- How to run and manage containers
- How to map ports between host and container
- How to check network interfaces using `ip address`
- How to create a macvlan network in Docker
