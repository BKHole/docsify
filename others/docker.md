# docker 指令

## 创建 docker 镜像

```
docker build . -t test:latest
```

- build：创建 docker 镜像
- .：使用当前目录下的 Dockerfile 文件
- -t：使用 tag 标记版本
- docsify-image:latest：创建名为 docsify-image 的镜像，并标记为 latest 版本

## 创建 docker 容器

基于 test:latest 镜像创建容器，将服务器 88 端口映射容器 80 端口

```
docker run -d -p 88:80 --name test-container test:latest
```

- run：创建并运行 docker 容器
- -d： 后台运行容器
- -p： 端口标记
- 88:80：冒号前，本地/服务器端口，冒号后，容器端口；这里意思是将当前服务器的 88 端口，映射到容器的 80 端口
- --name：给容器命名，便于之后定位容器，命名可选
- test:latest：基于 test:latest 版本的镜像创建容器

## nginx 代理

基于 jwilder/nginx-proxy 镜像建立容器，将服务器 80 端口映射容器 80 端口，nginx 容器监听 80 端口

```
docker run -d -p 80:80 -v /var/run/docker.sock:/tmp/docker.sock:ro jwilder/nginx-proxy
```

## 域名绑定

基于 test 镜像创建容器，并绑定 abc.com 域名到该容器，访问该域名就能看到容器内容

```
docker run -e VIRTUAL_HOST=abc.com test
```

- e：环境指令标记
- VIRTUAL_HOST：域名变量

## nginx

docker 使用 nginx 时，可以将以下目录映射本地目录，方便编辑

```
:/var/log/nginx #nginx日志目录
:/etc/nginx #nginx配置目录
:/usr/share/nginx #项目目录
```
