# docker-stack-demo
用docker stack进行服务编排。

## 安装宿主机
安装宿主机，这里以ubuntu为例。

## 安装docker环境
sudo apt install docker.io

## 设置docker自动启动
sudo systemctl start docker
sudo systemctl enable docker

## 添加docker用户
sudo addgroup --system docker
sudo adduser $USER docker
newgrp docker

## 安装 portainer 用户界面（可选）
docker volume create portainer_data
docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer

## 开启swarm
docker swarm init --advertise-addr [ip]
docker swarm join-token manager

## 部署stack
chmod +x deploy.sh
./deploy.sh