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

### 8. Inspect Bridge Network
```bash
sudo docker inspect bridge
```
--- 

## 📸 Screenshots

### Docker Install
![Docker Install](Docker%20install.jpg)

### Docker Run Nginx
![Docker Run](docker%20run%20nginx.jpg)

### Docker PS & Containers
![Docker PS](docker%20ps%20%26%20containers%20run.jpg.png)

### Docker Exec
![Docker Exec](docker%20exec%20.jpg.png)

### IP Address
![IP Address](Ip%20address%20show.jpg)

### Docker Network Create
![Network Create](docker%20network%20create.jpg)

### Docker Inspect Bridge
![Inspect Bridge](docker%20inspect%20bridge.jpg)

## 📝 What I Learned
- How to install Docker on Ubuntu
- How to run and manage containers
- How to map ports between host and container
- How to check network interfaces using `ip address`
- How to create a macvlan network in Docker
