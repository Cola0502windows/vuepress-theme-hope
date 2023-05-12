---
title: VM 虚拟机 CentOS7 配置静态 IP
icon: launch
---
# VM 虚拟机 CentOS7 配置静态 IP

> Author: Cola
>
> Time: 2023.02.03 20:00 PM
>
> To：VM 虚拟机 CentOS7 配置静态 IP

> Features:
>
> - [x] 结构
> - [ ] 上传 DOC

## 一、为什么要在CentOS中配置配置静态ip地址？

> 因为在vm中的centOS中的ip地址在没有重启的情况下发生变化，虚拟机的ip租约过期后，ip就会重新分配，从而造成ip地址的自行变化。为了应用方便和ip地址的固定，就需要设置centOS的静态ip,也就是固态ip地址，那我们之前的连接都会失效

## 二、CentOS7 配置静态 IP

### 2.1 参数配置

> 需要确保虚拟机网络适配器为 `NAT` 模式

![image-20230203200650009](/image-20230203200650009.png)

> 查看网络参数

![image-20230203200721305](/image-20230203200721305.png)

![image-20230203200734875](/image-20230203200734875.png)

![image-20230203200746203](/image-20230203200746203.png)

> 配置参数
>
> 1. 进入 `cd /etc/sysconfig/network-scripts/`
> 2. 使用 vim 编辑器打开配置文件 `vim ifcfg-ens33`

![image-20230203200927462](/image-20230203200927462.png)

> 首先更改`BOOTPROTO`为`static`
>
> 其次更改`ONBOOT`为`yes`，用于设置是否开机启动
>
> 然后更改 
>
> - 静态 IP （IPADDR）
> - 子网掩码 （NETMASK）
> - 网关 IP （GATEWAY）
> - DNS

> 静态 IP （IPADDR）,需要和配置图中的子网 IP 在同一网段即 `192.168.171.*` (* 为 0 ~ 255)

![image-20230203201225055](/image-20230203201225055.png)

> 子网掩码 （NETMASK），为配置图中的子网掩码 `255.255.255.0`

> 网关 IP ，为配置图中的网关 IP `192.168.171.2`

> DNS 通常为 `8.8.8.8`

![image-20230203201452060](/image-20230203201452060.png)

> 重启服务 `service network restart`

### 2.2 验证

> 输入 `ip addr` 查看网络信息
