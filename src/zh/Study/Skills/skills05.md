---
title: 使用 Microsoft 官方提供的 VPS 实现对Windows OS 的激活以及 Office 的激活
icon: launch
---
# 使用 Microsoft 官方提供的 VPS 实现对Windows OS 的激活以及 Office 的激活

> Author: Cola
>
> Time: 2022.11.08 15.45
>
> To：使用 Microsoft 官方提供的 VPS 实现对Windows OS 的激活以及 Office 的激活Linux 下使用 pm2 实现端口常驻

> Features:
>
> - [X] vps 概述
> - [X] vps 的安装以及使用

**1.[office 软件部署工具](https://www.microsoft.com/en-us/download/details.aspx?id=49117)**

![1668067932363](/1668067932363.png)

- 在桌面新建 `office`文件用于初始化
- 使用 `officeDeploymentTool` 对 `office`进行初始化

![1668067972002](/1668067972002.png)

![1668067994997](/1668067994997.png)

![1668068011630](/1668068011630.png)

**2.[office 版本自定义工具](https://config.office.com/deploymentsettings)**

- 注意要选择对应版本

![1668068023298](/1668068023298.png)

![1668068036829](/1668068036829.png)

![1668068050592](/1668068050592.png)

- 将生成的 `config.xml` 文件添加到 `office` 文件夹中

![image.png](/1668068171648.png)

**3.[基于KMS的 GVLK：](https://learn.microsoft.com/zh-cn/deployoffice/vlactivation/gvlks)**

**下载命令：**

```shell
setup /download config.xml
```

![1668068106914](/1668068106914.png)

**安装命令:**

```shell
setup /configure config.xml
```

![1668068151869](/1668068151869.png)

**office 激活命令: (CMD以管理员运行)**

进入到你的office安装目录下

![1668068171648](/1668068171648.png)

`cd C:\Program Files \Microsoft Office\Office16`

或者是

`cd C:\Program Files (x86)\Microsoft Office\Office16`

进入以后

执行以下2个命令即可完成：

```shell
cscript ospp.vbs /sethst:kms.03k.org

cscript ospp.vbs /act
```

![1668068190582](/1668068190582.png)

![1668068204649](/1668068204649.png)
