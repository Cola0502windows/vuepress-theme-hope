---
title: 使用 Docker 安装常用服务
icon: launch
---
# 使用 Docker 安装常用服务

> Author: Cola
>
> Time: 2023.2.04 14:14 PM
>
> To：使用 Docker 安装常用服务

> Features:
>
> - [x] 结构
> - [ ] 上传 Doc

### 一、开发类

> - [x] MySQL 
> - [x] Tomcat
> - [x] Redis
> - [ ] JDK
> - [ ] Nginx

### 1.1 MySQL

> - [x] 拉取镜像
> - [x] 创建 volume 和 network
> - [x] 创建容器
> - [x] 配置

#### 1.1.1 拉取镜像

> 使用命令 `docker pull mysql:5.7` 进行镜像的拉取镜像

#### 1.1.2 创建 volume 和 network

> - 使用命令 `docker volume create mysql3306` 创建 volume
> - 使用命令 `docker network create mysql-net` 创建 network

#### 1.1.3 创建容器

> 使用命令  `docker run -d --name mysql3306 -e MYSQL_ROOT_PASSWORD=root -v mysql3306:/var/lib/mysql -p 3306:3306 --network=mysql-net [镜像 id]`

```dockerfile
docker run -d --name mysql3306 
-e MYSQL_ROOT_PASSWORD=root 
-v mysql3306:/var/lib/mysql 
-p 3306:3306 
--network=mysql-net [镜像 id]
```

#### 1.1.4 配置

> - 配置编码格式
>   - 通过 `docker exec -it [容器 id] bash` 进入容器
>   - 进入配置目录 `cd /etc/mysql/`
>   - 使用 vim 对配置文件进行编辑`vim my.cnf`
>
> 注意：如果 vim 不可用需要使用下列命令进行安装
>
> - `apt-get update`
> - `apt-get install vim`

```xml
[client]
default_character_set=utf8
[mysqld]
collation_server = utf8_general_ci
character_set_server = utf8
```

### 1.2 Tomcat

> - [x] 拉取镜像
> - [x] 创建 volume 和 network
> - [x] 创建容器
> - [x] 配置

#### 1.2.1 拉取镜像

> 使用命令 `docker pull billygoo/tomcat8-jdk8` 拉取镜像

#### 1.2.2 创建 volume 和 network

> - 使用命令 `docker volume create tomcat8_80` 创建 volume
> - 使用命令 `docker network create tomcat-net` 创建 network

#### 1.2.3 创建容器

> 使用命令 `docker run -d --name tomcat8_80 -v tomcat8_80:/usr/local/tomcat/webapps -p 80:8080 --network=tomcat-net billygoo/tomcat8-jdk8`

```dockerfile
docker run -d --name tomcat8_80 
-v tomcat8_80:/usr/local/tomcat/webapps 
-p 80:8080 
--network=tomcat-net billygoo/tomcat8-jdk8
```

> 在主机的 `/var/lib/docker/volumes/tomcat8_80/_data/HelloWorld/HelloTomcat.html` 目录下创建测试目录

![image-20230204160939651](/image-20230204160939651.png)

#### 1.2.4 配置

> - 配置静态资源 `cd /usr/local/tomcat/conf` 后使用 vim 编辑 `server.xml` 为其添加 `<Context docBase="[静态资源绝对路径]" path="" debug="0" reloadable="true"/>`
> - 返回主机重启 `tomcat` 服务

![image-20230204160846084](/image-20230204160846084.png)

![image-20230204160752908](/image-20230204160752908.png)

![image-20230204160818155](/image-20230204160818155.png)

### 1.3 Redis

> - [x] 拉取镜像
> - [x] 创建 volume 和 network
> - [x] 创建容器
> - [x] 配置

#### 1.3.1 拉取镜像

> 使用命令 `docker pull redis:6.0.8` 拉取镜像

#### 1.3.2 创建 volume 和 network

> - 使用命令 `docker volume create redis6_6379` 创建 volume
> - 使用命令 `docker network create redis-net` 创建 network

#### 1.3.3 创建容器

> - 进入主机中 volume 目录配置 `redis.conf`
>   - 进入 `cd/var/lib/docker/volumes/redis6_6379/_data` 后创建 `redis.conf` 部分配置见 1.1.4
> - 使用命令  `docker run -d --name redis6_6379 -v redis6_6379:/usr/local/redis -p 6379:6379 --network=redis-net [镜像 id] redis-server /usr/local/redis/redis.conf `

```dockerfile
docker run -d --name redis6_6379 
-v redis6_6379:/usr/local/redis 
-p 6379:6379 
--network=redis-net [镜像 id] redis-server /usr/local/redis/redis.conf
```

#### 1.3.4 配置

```xml
bind 127.0.0.1 #注释掉这部分，使redis可以外部访问
daemonize no #用守护线程的方式启动
requirepass 你的密码 #给redis设置密码
appendonly yes #redis持久化　　默认是no
tcp-keepalive 300 #防止出现远程主机强迫关闭了一个现有的连接的错误 默认是300
```

### 1.4 JDK

> - [x] 拉取镜像
> - [x] 创建 volume 和 network
> - [x] 创建容器
> - [x] 配置

#### 1.4.1 拉取镜像

#### 1.4.2 创建 volume 和 network

#### 1.4.3 创建容器

#### 1.4.4 配置

### 1.5 Nginx

> - [x] 拉取镜像
> - [x] 创建 volume 和 network
> - [x] 创建容器
> - [x] 配置

#### 1.5.1 拉取镜像

#### 1.5.2 创建 volume 和 network

#### 1.5.3 创建容器

#### 1.5.4 配置

## 二、应用类

> - [x] Alist

### 2.1 Alist

> [Alist](https://github.com/alist-org/alist)是一个支持多存储的文件列表程序，使用 Gin 和 Solidjs的 GitHUb 开源项目。
>
> - [官网](https://github.com/alist-org/alist)
> - [帮助文档](https://alist.nn.ci/zh/guide/install/docker.html)

> - [x] 拉取镜像
> - [x] 创建 volume 和 network
> - [x] 创建容器
> - [x] 配置

#### 1.1.1 拉取镜像

> 使用命令 `docker pull xhofe/alist:latest` 拉取镜像

#### 1.1.2 创建 volume 和 network

> - 使用命令 `docker volume create alist_5244` 创建 volume
> - 使用命令 `docker network create alist-net` 创建 network

#### 1.1.3 创建容器

> 使用命令 `docker run -d  --name=alist_5244 --restart=always -v alist_5244:/opt/alist/data -p 5244:5244 -e PUID=0 -e PGID=0 -e UMASK=022 --network=alist-net xhofe/alist:latest`

```dockerfile
docker run -d  
--name=alist_5244 
--restart=always 
-v alist_5244:/opt/alist/data 
-p 5244:5244 
-e PUID=0 -e PGID=0 -e UMASK=022 
--network=alist-net xhofe/alist:latest
```

> 查看管理员信息 `docker exec -it [容器 id] ./alist admin`

![image-20230204162849735](/image-20230204162849735.png)

![image-20230204162947174](/image-20230204162947174.png)

#### 1.1.4 配置

> TODO

