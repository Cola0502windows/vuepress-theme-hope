---
title: IDEA 下有关 Maven 的配置
icon: launch
---

> Author: Cola  
> Time: 2023.1.29 13:26 PM
> To: IDEA 下有关 Maven 的配置

## Features

> - [x] 完善大致结构
> - [ ] 上传至 DOC

## 一、 IDEA 下有关 Maven 的配置

> - [ ] IDEA 创建 Maven 工程
> - [ ] 为特定项目添加国内镜像
> - [ ] IDEA 下 Maven 离线开发
> - [ ] 聚合工程下 Maven 的打包（分模块）

### 1.1 IDEA 创建 Maven 工程

> IDEA 创建 Maven 工程

### 1.2 为特定项目添加国内镜像

> 有时候我们需要在不修改 Maven 配置的情况下，对某些项目使用指定的镜像仓库，这个时候我们
>
> 可以在对应项目的 `POM` 文件中添加如下配置：

```xml
    <repositories>
        <repository>
            <id>nexus-aliyun</id>
            <name>nexus-aliyun</name>
            <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
            <releases>
                <enabled>true</enabled>
            </releases>
            <snapshots>
                <enabled>false</enabled>
            </snapshots>
        </repository>
    </repositories>

    <pluginRepositories>
        <pluginRepository>
            <id>public</id>
            <name>aliyun nexus</name>
            <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
            <releases>
                <enabled>true</enabled>
            </releases>
            <snapshots>
                <enabled>false</enabled>
            </snapshots>
        </pluginRepository>
    </pluginRepositories>
```



### 1.3 IDEA 下 Maven 离线开发

> IDEA 下 Maven 离线开发

### 1.4 聚合工程下 Maven 的打包（分模块）

> 聚合工程下 Maven 的打包（分模块）
