---
title: Linux 下使用 PM2 实现端口常驻
icon: launch
---

# Linux 下使用 PM2 实现端口常驻

> Author: Cola
>
> Time: 2022.11.08 15.45
>
> To：Linux 下使用 PM2 实现端口常驻记录

> Features:
>
> - [X] PM2 概述
> - [X] PM2 的安装以及使用

## PM2 概述

> [PM2 官网](https://pm2.io/)
>
> 一旦你认真对待生产，你需要确保你的应用程序正常运行，没有错误，没有性能问题，也没有停机时间。
>
> 这就是我们创建PM2 Plus的原因。它是一组功能，用于强化当前的 PM2 运行时进程管理器和监视生产中的应用程序。
>
> 使用PM2 Plus，您可以获得：
>
> * 实时监控 Web 界面
> * 问题和异常跟踪
> * 部署报告
> * 实时日志
> * 电子邮件和 Slack 通知
> * 自定义指标监控
> * 自定义操作中心

## PM2 的安装以及使用

- 安装

```shell
sudo npm  install -g pm2
```

- 使用

> 在需要进行常驻的应用程序根目录下创建对应的 js 文件
>
> 此处以 hexo 博客系统为例子：
>
> 在博客根目录下创建一个 JavaScript 运行脚本 `hexo_run.js`

```javascript
//run
const { exec } = require('child_process')
exec('hexo server -p 80',(error, stdout, stderr) => {
        if(error){
                console.log('exec error: ${error}')
                return
        }
        console.log('stdout: ${stdout}');
        console.log('stderr: ${stderr}');
})
```

> 启动 `pm2 start hexo_run.js`

> 结束 `pm2 stop hexo_run.js`

> 列表 `pm2 ls`
