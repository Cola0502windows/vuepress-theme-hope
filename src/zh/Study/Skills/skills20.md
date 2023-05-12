---
title: 使用 Docker容器配置 MySQL 主从数据库
icon: launch
---
# 使用 Docker容器配置 MySQL 主从数据库

> Author: Cola
>
> Time: 2023.2.01 16:54 PM
>
> To：Docker Mysql数据库主从同步配置详细

> Features:
>
> - [x] 结构
> - [ ] 上传 Doc

## 一、具体操作

> - [x] 拉取镜像
> - [x] 创建 volume 和 network
> - [x] 创建容器
> - [x] 配置节点
>   - [x] 配置主节点
>   - [x] 配置从节点
> - [x] 主节点授权 slave
> - [x] 从节点运行 slave

### 1.1 拉取镜像

> 使用 docker pull 命令拉去 MySQL镜像（此处使用版本为 5.7） `docker pull mysql:5.7`

![image-20230202140203312.png](/image-20230202140203312.png)

### 1.2 创建 volume 和 network

> -  volume  
> - network

#### 1.2.1 volume

> 创建 volume 容器卷 
>
> - 主数据库（3307）：`docker volume create mysql3307`
> - 从数据库（3308）：`docker volume create mysql3308`

![image-20230202140241145](/image-20230202140241145.png)

#### 1.2.2 network

> 创建 docker 网络 `docker network create mysql-net`

![image-20230202140309463](/image-20230202140309463.png)

### 1.3 创建容器

> - 主数据库：`docker run -d --name mysql3307 -e MYSQL_ROOT_PASSWORD=root -v mysql3307:/var/lib/mysql -p 3307:3306 --network=mysql-net [mysql 镜像]`
> - 从数据库：`docker run -d --name mysql3308 -e MYSQL_ROOT_PASSWORD=root -v mysql3308:/var/lib/mysql -p 3308:3306 --network=mysql-net [mysql 镜像]`

![image-20230202140427952](/image-20230202140427952.png)

### 1.4 配置节点

> 通过 `docker exec -it [容器 id] bash` 进入容器后，因为默认情况下我们创建的 MySQL 容器中并没有安装 `vim` 命令，所以我们先安装 `vim`:
>
> - `apt-get update`
> - `apt-get install vim`

![image-20230202141702365](/image-20230202141702365.png)

> 然后通过 `vim` 命令对 MySQL 的配置文件 `my.cnf` 进行配置。
>
> - 通过命令 `cd /etc/mysql/` 进入 mysql 目录下后用 `vim my.cnf` 对配置文件进行配置。



#### 1.4.1 配置主节点

> - `docker exec -it [主数据库容器 id] bash`
> - `cd /etc/mysql/`
> - `vim my.cnf`

将下段内容配置到 my.cnf 中

```xml
[client]
default_character_set=utf8
[mysqld]
server-id=1 
collation_server = utf8_general_ci
character_set_server = utf8
log-bin=mysql-bin
```

> 通过 `cat my.cnf` 查看是否配置成功。

> 退出当前容器后`docker restart [容器 id]`重启容器

![image-20230202141911216](/image-20230202141911216.png)

#### 1.4.2 配置从节点

> - `docker exec -it [从数据库容器 id] bash`
> - `cd /etc/mysql/`
> - `vim my.cnf`

将下段内容配置到 my.cnf 中

```xml
[client]
default_character_set=utf8
[mysqld]
collation_server = utf8_general_ci
character_set_server = utf8
server-id=2  
log-bin=mysql-slave-bin   
relay_log=edu-mysql-relay-bin 
```

> 通过 `cat my.cnf` 查看是否配置成功。

> 退出当前容器后`docker restart [容器 id]`重启容器

![image-20230202141834969](/image-20230202141834969.png)

### 1.5 主节点授权 slave

> - 进入主数据库输入 `GRANT REPLICATION SLAVE ON *.* to 'slave'@'%' identified by '123456';`授权 slave这里表示创建一个slaver同步账号slave，允许访问的IP地址为%，%表示通配符
> - 使用 `show master status\G;`查看状态，记住File、Position的值，在Slave中将用到。

![image-20230202141951427](/image-20230202141951427.png)

![image-20230202142146338](/image-20230202142146338.png)

### 1.6 从节点运行 slave

> - 使用 `docker network inspect mysql-net | grep -A 3 'mysql3307' | grep 'IPv4Address'`查询出主数据库 ip 
> - 进入从数据库输入 `change master to master_host='[主数据库 ip]',master_user='slave',master_password='123456',master_log_file='[file]',master_log_pos=[pos],master_port=3306;`
> - `start slave;` 启动主从复制
> - `show slave status\G;` 查看状态

![image-20230202142237574](/image-20230202142237574.png)

![image-20230202142811136](/image-20230202142811136.png)

![image-20230202142834247](/image-20230202142834247.png)

> 使用数据库连接工具分别连接：
>
> - 主数据库：MySQL 3307
> - 从数据库：MySQL 3308

![image-20230202143012844](/image-20230202143012844.png)

> 在主库中创建测试表

![image-20230202143121060](/image-20230202143121060.png)

> 刷新从库

![image-20230202143200882](/image-20230202143200882.png)