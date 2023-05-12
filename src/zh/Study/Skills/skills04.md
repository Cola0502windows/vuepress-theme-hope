---
title: 新电脑环境下的开发环境的配置
icon: launch
---
# 新电脑环境下的开发环境的配置

> Author: Cola
>
> Time: 2022/9/23 12.20 PM
>
> To: 最近因为一些问题频繁的重装电脑每次都很麻烦，特此记录新电脑开发环境的搭建 😭😭（TODO 以后直接做个纯净的备份系统）

> Windows平台： Win11 22H2 专业版 (参见 （TODO Youtube 实现 Win 11 专业版激活）) (EX：[使用 Microsoft 官方提供的 VPS 实现对Windows OS 的激活以及 Office 的激活](http://43.143.184.147/zh/Study/Skills/skills05.html))
>
> MacOS平台: TODO
>
> CentOS: centOS7 (EX： [使用 VM 在 CentOS7 下安装 Docker](http://43.143.184.147/zh/Study/Skills/skills15.html))

![img](/buildPathimage.png)

>- [ ] 与 Alist 进行搭配
>
>- [ ] 进行离线备份
>
>- [x] 常用软件
>- [ ] 开发软件 IDEA 等及相关配置
>- [ ] 开发环境 Maven 等配置
>- [ ] 浏览器插件

## 常用软件


### 一， Windows

#### 1.1 常用软件

##### 1.1.1 微信

> **作用：用于日常交流以及办公**
>
> **下载地址**：[微信 Windows 官网下载](https://pc.weixin.qq.com/)

![image.png](/1663914429257-image.png)

##### 1.1.2 QQ

> **作用：用于 Emmm 怀念吧** 😄
>
> **下载**: [QQ Windows 官网下载](https://im.qq.com/pcqq)

##### 1.1.3 Clash for Windows

> 作用：科学上网 👀️
>
> **下载：**[calsh for windows 官网](https://cmejiaocheng.xyz/proxytools/)

![image.png](/1663909393227-image.png)

![image.png](/1663909414021-image.png)

##### 1.1.4 7-Zip

> **作用：小巧精致**的解压软件
>
> **下载：**[7-Zip GitHub 官方下载](https://github.com/mcmilk/7-Zip-zstd/releases)

> **如果出现访问被拒绝 尝试使用 以管理员身份运行程序**

![image.png](/1663909611261-image.png)

![image.png](/1663909614928-image.png)

##### 1.1.5 Chorme

> **作用：谷歌浏览器**
>
> **下载**： [Chorme 官网下载](https://www.google.cn/intl/en_uk/chrome/)

##### 1.1.6 Microsoft Edge

> 作用： Microsoft Edge 微软 Edge 浏览器
>
> 下载： [Edge 官网下载](https://www.microsoft.com/en-us/edge)

##### 1.1.7 Firefox

> **作用：火狐浏览器**
>
> **下载**：[Firefox 官网下载](https://www.mozilla.org/zh-CN/firefox/new/)

##### 1.1.8 Uninstall Tool

> 作用：非常好用的 卸载软件
>
> - 可用来卸载软件
> - 扫描注册表
> - 管理自启动项
>
> 下载：[Uninstall Tool 官网下载](https://crystalidea.com/uninstall-tool/download)

![image.png](/1663910001611-image.png)

![image.png](/1663910176758-image.png)

##### 1.1.9 Net DownLoad Manager

> 作用：一款轻巧的多线程下载器 (额外功能：参见 [使用 NDM 实现多线程下载](http://43.143.184.147/zh/Study/Skills/skills11.html))
>
> 下载：[Net DownLoad Manager 官网下载](https://www.neatdownloadmanager.com/index.php/en/)

![image.png](/1663910221562-image.png)

> Max Connections per DownLoad: 下载线程数
>
> Default User-Agent: 下载表头 （可配合直链助手下载相应资源)  👍
>
> DownLoad Directory: 文件保存位置
>
> Temporay Directory： 日志生成位置

![image.png](/1663910384980-image.png)

> 添加浏览器拓展实现下载资源的嗅探 例如可以用来直接下载图片

![image.png](/1663910443346-image.png)

##### 1.1.10 Snipaste

> **作用： Windows 上非常好用的截图软件**
>
> **下载**：[Snipaste 官网下载](https://github.com/Snipaste/feedback)

![image.png](/1663910596803-image.png)

> 贴图置顶功能很实用 👍

![image.png](/1663910682375-image.png)

![image.png](/1663910714358-image.png)

##### 1.1.11 Windows Terminal

> 作用：界面超美观的 Windows Terminal
>
> 下载：
>
> - [Windows Terminal 官网](https://github.com/microsoft/terminal/releases)  安装包方式
> - 直接在 Microsoft Stroe 中搜索 Terminal 即可

![image.png](/1663910772932-image.png)

![image.png](/1663910915520-image.png)

##### 1.1.12 ioDraw

> 作用：可用来做思维导图
>
> 下载：[ioDraw GitHub 官方仓库](https://github.com/ixiaoyang8/iodraw/releases)

##### 1.1.13 Sublime Text

> 作用：好用的文本编辑器 可提供代码高显示
>
> 下载：[Sublime Text 官网下载](https://www.sublimetext.com/download)

- 汉化

> 首先安装 package control

![image.png](/1663911467248-image.png)

![image.png](/1663911471580-image.png)

![image.png](/1663911478459-image.png)

![image.png](/1663911486351-image.png)

> 键入 chinese 搜索 中文汉化插件

![image.png](/1663911520172-image.png)

![image.png](/1663911526833-image.png)

- 安装 编码插件

> 键入 utf-8

![image.png](/1663911555197-image.png)

![image.png](/1663911559812-image.png)

##### 1.1.14 Typora

> 作用： 非常好用的 MarkDown 编辑器 👍 (EX：[记录破解 Typora](http://43.143.184.147/zh/Study/Skills/skills14.html))
>
> 下载：[Typora 官网下载](https://typora.io/)
>
> 官方文档：TODO 主 Edge 收藏栏夹 或者 To XiaoEr Wx
>

![image.png](/1663911640589-image.png)

##### 1.1.15 BandZip

> 作用：一款好用的压缩软件
>
> 下载；[BandZip 官网](https://www.bandisoft.com/bandizip/)

##### 1.1.16 阿里云盘

> 作用：一款实用的网盘
>
> 下载：[阿里云盘](https://www.aliyundrive.com/)

##### 1.1.17 Steam

> 作用：Steam 游戏平台
>
> 下载：[Steam](https://store.steampowered.com/)

##### 1.1.18 MyDockFinder

> 作用：在 Windows 下实现类 Mac 风格 Nice
>
> 下载：Steam 中查找即可

##### 1.1.19 网易云音乐

> 作用：Music
>
> 下载：[网易云音乐](https://music.163.com/)

##### 1.1.20  Telegram

> 作用：Telegram 电报
>
> 下载：[Telegram](https://telegram.org/)

##### 1.1.21  Discord

> 作用：Discord 聊天
>
> 下载：[Discord](https://discord.com/download)

##### 1.1.22  思源笔记

> 作用：一款好用的笔记软件
>
> 下载：[思源笔记](https://b3log.org/siyuan/)

##### 1.1.23 Office 365

> 作用：Office 365 办公
>
> 下载：（EX：[使用 Microsoft 官方提供的 VPS 实现对Windows OS 的激活以及 Office 的激活](http://43.143.184.147/zh/Study/Skills/skills05.html)）



### 二， 开发软件

> EX： [记录破解 IDEA 等开发工具](http://43.143.184.147/zh/Study/Skills/skills13.html)

##### 2.1.1 Idea

> 作用： Java 集成开发器
>
> 下载：[JET BRAINS 官网下载](https://www.jetbrains.com/zh-cn/idea/download/other.html)

##### 2.1.2 DataGrip

> 作用： Mysql 数据库开发
>
> 下载：[JET BRAINS 官网下载](https://www.jetbrains.com/zh-cn/idea/download/other.html)

##### 2.1.3 WebStorm

> 作用： 前端开发平台
>
> 下载：[JET BRAINS 官网下载](https://www.jetbrains.com/zh-cn/idea/download/other.html)

##### 2.1.4 Pycharm

> 作用：Python 开发平台
>
> 下载：[JET BRAINS 官网下载](https://www.jetbrains.com/zh-cn/idea/download/other.html)

##### 2.1.5 Visual Studio Code

> 作用：插件机器丰富且强大的编辑器
>
> 下载：[Microsoft 官网下载](https://code.visualstudio.com/)

##### 2.1.6 Visual Studio 2022

> 作用： C 开发环境
>
> 下载：[ Microsoft 官网下载](https://visualstudio.microsoft.com/zh-hans/vs/)

##### 2.1.7 Eclipse

> 作用：免费的 Java 集成开发器
>
> 下载：[Eclipse 官网下载](https://www.eclipse.org/downloads/packages/release)

TODO 详细下载 以及 初始 SSM 环境的搭建请参见 ColaBlog

##### 2.1.8 Oracle VM VirtualBox

> 作用： Oracle 推出的强大的虚拟机平台
>
> 下载：[Oracle 官网下载](https://www.virtualbox.org/)
>
> ISO 文件下载网站推荐：[Microsoft 官网 ISO 下载](https://my.visualstudio.com/Downloads/Featured?mkt=zh-cn)

##### 2.1.9 Xftp

> 作用： 用于与服务器之间文件可视化操作
>
> 下载：[Xftp 官网下载](https://www.xshell.com/zh/free-for-home-school/)

![image.png](/1663912611016-image.png)

##### 2.1.10 Xshell

> 作用： 用于与服务器之间 终端 ssh 通信
>
> 下载：[Xftp 官网下载](https://www.xshell.com/zh/free-for-home-school/)

##### 2.1.11 GitHub Desktop

> 作用：GitHub 推出的可视化 Git 交互平台
>
> 下载：[GitHub 官网下载](https://desktop.github.com/)

##### 2.1.12 VMware Workstation Pro

> 作用：VMware Workstation Pro 一款好用的虚拟机软件
>
> 下载：[ VMware](https://www.vmware.com/cn/products/workstation-pro.html)

##### 2.1.13 Finallshell

> 作用：多功能远程终端连接工具
>
> 下载：[Finallshell](https://www.hostbuf.com/)

##### 2.1.14 DockerDeskTop

> 作用：Docker 官方可视化工具
>
> 下载：[DockerDeskTop](https://docs.docker.com/desktop/install/windows-install/)

##### 2.1.15 ToolBox

> 作用：一款 JetBrains 官方出品的工具箱可用于管理 IDEA 等
>
> 下载：[ToolBox](https://www.jetbrains.com/zh-cn/toolbox-app/)

##### 2.1.16 Navicat

> 作用：Navicat Premium 是一套多连接数据库开发工具，让你在单一应用程序中同时连接多种类型的数据库：MySQL、MariaDB、MongoDB、SQL Server、SQLite、Oracle 和 PostgreSQL，可一次快速方便地访问所有数据库。
>
> 下载：[Navicat](https://navicat.com.cn/products/navicat-premium)

### 三， 开发环境

##### 3.1.1 Git

> 作用： 高效的团队协作开发工具 可提供版本支持 代码回滚等
>
> 下载：[Git 官网下载](https://git-scm.com/downloads)

TODO  user config 的配置  公钥密钥的下载和上传  本地仓库和远程仓库的对接

##### 3.1.2 Jdk

> 作用：Java 开发者工具包
>
> 下载：
>
> - [Oracle 官网下载](https://www.oracle.com/java/technologies/downloads/)
> - IDEA 中下载

##### 3.1.3 Python

> 作用：Python 运行环境
>
> 下载：[Python 官网下载](https://www.python.org/downloads/windows/)

##### 3.1.4 Node.js

> 作用：源和跨平台的 JavaScript 运行时环境
>
> 下载：[Node.js 官网](http://nodejs.cn/download/)

##### 3.1.5 Maven

> 作用：用于管理 jar 包
>
> 下载：[Maven 官网](https://maven.apache.org/download.cgi)

TODO 配置 usersetting 中的本地 maven 仓库 及 换源

##### 3.1.6 Mysql

> 作用：数据库服务
>
> 下载：[Oracle Mysql 官网下载](https://downloads.mysql.com/archives/community/)

TODO 初始化数据库 注册服务 修改密码

##### 3.1.7 Tomcat

> 作用：Web 服务器
>
> 下载：[Tomcat 官网](https://tomcat.apache.org/download-90.cgi)

TODO 修改 config 中的 uft 编码以解决 Windwos 下因编码问题造成的乱码问题

##### 3.1.8 Adb

> 作用： Android 玩家必备
>
> 下载：[Android Developers 官网下载](https://developer.android.google.cn/studio/command-line/adb?hl=zh-cn)

TODO 建立自己的 APK 仓库 便于管理 说不定那天可以换手机  👀️

##### 3.1.9 Vagrant

> 作用：搭配 VM 虚拟机快速搭建 虚拟机环境
>
> 下载：[Vagrant 官网下载](https://www.vagrantup.com/downloads)

TODO 知乎之 Vagrant 超详细入门

##### 3.1.10 Redis

> 作用：Nosql 数据库
>
> 下载：[Redis](https://github.com/redis/redis/releases)

### 四， 设计软件

##### 4.1.1 Adobe Pr

> 作用： Adobe 旗下非常强大的影视剪辑软件
>
> 下载：
>
> - [Adobe 官网下载](https://www.adobe.com/cn/products/premiere.html)
> - 百度网盘资源下载

TODO 整理希捷硬盘中的目录结构

##### 4.1.2 Adobe Ps

> 作用： Adobe 旗下非常强大的图片处理
>
> 下载：
>
> - [Adobe 官网下载](https://www.adobe.com/cn/products/photoshop.html)
> - 百度网盘资源下载

### 五， 操作系统的使用技巧

##### 5.1.1 Windows 剪切板

> 作用：记录历史粘贴内容 表情输入
>
> 使用： Win + V 键 开启

![image.png](/1663914131196-image.png)

##### 5.1.2 Hyper-V 虚拟技术

> 作用: Microsoft 下的用于支持虚拟器的一些技术服务
>
> 安装：

> 首先打开 Windows 设置

![image.png](/1663914252438-image.png)

![image.png](/1663914255234-image.png)

##### 5.1.3 适用于 Linux 的 Windows 子系统

> 作用： Microsoft 官方推出的 Linux 子系统可在 Windows 上通过命令行的方式运行 原生 Linux

![image.png](/1663914350680-image.png)

TODO 完善 适用于 Windows 的 Ubuntu 子系统

##### 5.1.4 Windows 沙盒

> 作用：完全独立的一个操作系统 在其中的任何操作都不会影响到主系统

![image.png](/1663914389878-image.png)



### 六、使用插件及网址导航

#### 6.1 IDEA 常用插件

> - [Atom Material Icons](https://plugins.jetbrains.com/plugin/10044-atom-material-icons)
> - [Gitee](https://plugins.jetbrains.com/plugin/11491-gitee)
> - [CodeGlance Pro](https://plugins.jetbrains.com/plugin/18824-codeglance-pro)
> - [Chinese Simplified](https://plugins.jetbrains.com/plugin/13710-chinese-simplified-language-pack----)
> - [GitToolBox](https://plugins.jetbrains.com/plugin/7499-gittoolbox)
> - [MyBatis Log](https://plugins.jetbrains.com/plugin/13905-mybatis-log)
> - [Rainbow Brackets](https://plugins.jetbrains.com/plugin/10080-rainbow-brackets)
> - [Restful Fast Request](https://plugins.jetbrains.com/plugin/16988-restful-fast-request)
> - []()
> - []()
> - []()

##### 6.1.1 Atom Material Icons

> 可以提供丰富的 Icon 图标

##### 6.1.2 Gitee

> 拓展 IDEA VCS 功能使其支持 Gitee

##### 6.1.3 CodeGlance Pro

> 提供代码 Map 导航

##### 6.1.4 Chinese Simplified

> 汉化

##### 6.1.5 GitToolBox

> 搭配 Git 使用

##### 6.1.6 MyBatis Log

> 记录发送的 SQL

##### 6.1.7 Rainbow Brackets

> 彩虹括号

##### 6.1.8 Restful Fast Request

> 超级好用的 API 接口测试工具（类似于 PostMan）

#### 6.2 Windows 插件 （Microsoft Store ）

> - [Tools]()
> - []()
> - []()

##### 6.2.1 Tools

> a

##### 6.2.2

> b

#### 6.3 浏览器插件

> - [iTabl](https://chrome.google.com/webstore/detail/itab%E6%96%B0%E6%A0%87%E7%AD%BE%E9%A1%B5/mhloojimgilafopcmlcikiidgbbnelip)
> - [TamperMonkey](https://www.tampermonkey.net/)
> - [SendMsg]()

##### 6.3.1 iTab

> 一款好用的导航

##### 6.3.2 TamperMonkey

> 油猴脚本
>
> - [CSDN 过滤](https://greasyfork.org/zh-CN/scripts/378351-%E6%8C%81%E7%BB%AD%E6%9B%B4%E6%96%B0-csdn%E5%B9%BF%E5%91%8A%E5%AE%8C%E5%85%A8%E8%BF%87%E6%BB%A4-%E4%BA%BA%E6%80%A7%E5%8C%96%E8%84%9A%E6%9C%AC%E4%BC%98%E5%8C%96-%E4%B8%8D%E7%94%A8%E5%86%8D%E7%99%BB%E5%BD%95%E4%BA%86-%E8%AE%A9%E4%BD%A0%E4%BD%93%E9%AA%8C%E4%BB%A4%E4%BA%BA%E6%83%8A%E5%96%9C%E7%9A%84%E5%B4%AD%E6%96%B0csdn)
> - [直链下载助手](https://greasyfork.org/zh-CN/scripts/418182-%E7%99%BE%E5%BA%A6%E7%BD%91%E7%9B%98%E7%AE%80%E6%98%93%E4%B8%8B%E8%BD%BD%E5%8A%A9%E6%89%8B-%E7%9B%B4%E9%93%BE%E4%B8%8B%E8%BD%BD%E5%A4%8D%E6%B4%BB%E7%89%88)
