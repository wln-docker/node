#Wlniao Node.js Docker Image

### Base Docker Image

* debian:jessie

### 构建 Build

> git clone https://github.com/wln-docker/node.git /tmp/node && docker build --no-cache -t wlniao/node:v0.10.41 /tmp/node/v0.10.41


### 如何使用 How to Use

> docker run --name container-name -e WLN_GIT=source-git -d wlniao/node:v0.10.41
