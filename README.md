# Biuld Kubernetes Cluster Locally with Minikube

## 1. Launch an EC2 Instance
![image alt](https://github.com/souravhajra123/ElevateLabsTask5/blob/1b935d0a4d737266b87ce82a01daa3a410d0517b/images/1.JPG)

## 2. Connect to the Instance
![image alt](https://github.com/souravhajra123/ElevateLabsTask5/blob/275857f403429fe5dc8dbfdb8ba3a31a15b7ad1f/images/2.JPG)

## 3. Update the Instance
```bash
sudo apt-get update
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask5/blob/275857f403429fe5dc8dbfdb8ba3a31a15b7ad1f/images/3.JPG)

## 4. Install `Docker`
```bash
nano docker.sh     # `ctrl+s` to save the file, `ctrl+x` to exit the nano editor mode
-------------------
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
sudo apt-get install docker-compose -y
sudo usermod -aG docker ubuntu
sudo chmod 777 /var/run/docker.sock
newgrp docker
sudo systemctl status docker
-----------------------
bash docker.sh
docker --version
docker-compose --version
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask5/blob/275857f403429fe5dc8dbfdb8ba3a31a15b7ad1f/images/4.JPG)

## 5. Install `Git`(Not required for the task but it will help you to push the files to GitHub repository)
```bash
sudo apt-get install git
git --version
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask5/blob/c9896d6d84dd963a5d45f8b6cb7379cc14b7ee9a/images/5.JPG)

## 6. Install `Minikube`
```bash
wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo cp minikube-linux-amd64 /usr/local/bin/minikube
sudo chmod +x /usr/local/bin/minikube
minikube version
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask5/blob/c9896d6d84dd963a5d45f8b6cb7379cc14b7ee9a/images/6.JPG)

## 7. Install `kubectl`
```bash
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
chmod +x kubectl
sudo mv kubectl /usr/local/bin/
kubectl version
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask5/blob/c9896d6d84dd963a5d45f8b6cb7379cc14b7ee9a/images/7.JPG)
