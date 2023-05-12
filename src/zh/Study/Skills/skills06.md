---
title:  Hexo 博客系统的搭建以及使用
icon: launch

---

# Hexo 博客系统的搭建以及使用

> Author: Cola
>
> Time: 2022.11.08 15.45
>
> To：Hexo 博客系统的搭建以及使用

> Features:
>
> - [x] 完成文档
> - [ ] 添加对 端口常驻的引用

**目录结构：**

> - 前言
> - 服务器环境搭建与配置
    >   - 安装 git 和 node.js **（必须）**
>   - 启用 Corepack **（可选）**
>   - 安装 Hexo CLI
>   - Hexo 常见命令
> - 博客主题的安装与配置
    >   - 安装主题
>   - 创建关于 页和文章的分类
>   - 自定义网站配置
>   - Particlex 主题使用说明
      >     - 主题安装
>     - 关闭 Hexo 默认的 highlight
>     - 头像及背景配置
>     - 导航栏配置
>     - 主页信息卡片
>     - 首页文档缩略配置
>     - 页脚配置
>     - Gitalk 评论系统
> - 页面渲染
    >   - 目录介绍
>   - 添加自定义 JS/CSS
>   - 实现流行背景，鼠标指针特效
>   - Hexo Markdown  语法补充
> - 使用 Github 搭建
    >   - 配置 SSH 密钥
>   - 更改默认分支
>   - 部署到 Github Pages
>   - 部署到 Vercel 或 Netlify 加速访问

## 一，前言

> Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。
> 学习 Markdown 语法可以看 [Github 官方文档](https://docs.github.com/cn/get-started/writing-on-github)

## 二，服务器环境搭建与配置

### 2.1 安装 git 和 node.js **（必须）**

- Git
  [Git官网](https://git-scm.com/downloads) 下载 Git完成后用 `git --version` 命令检查，有提示即安装正确
- Node.js
  [Node官网](https://nodejs.org/en/) 下载 Node.js，选择 LTS 版本，安装一路确认即可
  完成后用 `node -v` 和 `npm -v` 两个命令检查，有提示即安装正确

### 2.2 启用 Corepack **（可选）**

运行 `corepack enable` 启用 Corepack
启用后自动安装 Yarn 和 PNPM，这样以后的命令都可以换成自己喜欢的包管理器
这里是速度参考

![](/20220904094158.png)

虽然 PNPM 较快，但创建 Vue/React 项目时可能会有错误

### 2.3 安装 Hexo CLI

输入命令 `npm i -g hexo`， 用 `hexo -v` 检查安装
新建一个文件夹，作为博客目录，cd 进入文件夹，运行 `hexo init & npm i`

[Hexo 官方文档](https://hexo.io/zh-cn/docs/)

### 2.4 Hexo 常见命令

* 生成静态文件：`hexo g`
* 清除静态文件：`hexo cl`
* 在本地运行：`hexo s`
* 部署到网站：`hexo d`
* 生成静态文件并部署到网站：`hexo d -g` 或 `hexo g -d`
* 创建新文章：`hexo new <post-name>`  **`<post-name>` 为文件名**

**P.S.：创建新文章命令中的 `<post-name>`是文件名，标题在文章中的 title 参数中修改，文件名建议全部小写，若有大写字母，部署后部分主题可能会 404**

> **可搭配 Xftp 和 Xshell 管理文件和SSL**

## 三，博客主题的安装与配置

### 3.1 安装主题

首先在[这里](https://hexo.io/themes/)选择一个主题，选好主题后就要安装，在博客根目录下运行下面的命令将主题 Clone 到本地

```bash
git clone <theme-dir>.git themes\<theme-name>bash
```

> 访问 GitHub 可以使用加速器也可以参照之前的文章修改 host记录

`ipconfig /flushdns` 刷新 DNS 缓存，重启浏览器，应该可以打开 Github

安装完成后，在博客根目录下的 `_config.yml` 中设置 theme 参数为你的主题名称(主题文件夹名称)，就可以切换主题

### 3.2 创建关于 页和文章的分类

* Categories/Tags 文章分类
  **`<root>` 为你博客的根目录**
  输入命令 `hexo new page categories` 创建 Categories 页面，打开 `<root>\source\categories`下的 index.md 文件，在文章前添加 type 参数值为 `"categories"`
  输入命令 `hexo new page tags` 创建 Tags 页面，打开 `<root>\source\tags`下的 index.md 文件，在文章前添加 type 参数值为 `"tags"`
* About 关于页
  先按照创建文章分类的方法，创建 About 页面，然后在下面添加内容即可

### 3.3 自定义网站配置

打开博客根目录下的 `_config.yml`，下面是主要参数的介绍

```yaml
title: # 标题
subtitle: # 副标题
description: # 描述
keywords: # 关键字
author: # 作者
language: # 语言
timezone: # 时区
url: # 网址
root: # 根目录
permalink: # 文章链接格式
permalink_defaults: # 链接默认值
source_dir: # 源文件夹，内容的存储位置
public_dir: # 公用文件夹，静态文件的生成位置
tag_dir: # 标签目录
archive_dir: # 存档目录
category_dir: # 分类目录
skip_render: # 复制到原始路径，不进行渲染
new_post_name: # 新帖子的文件名格式
titlecase: # 将标题转换为小写1/大写2 *
external_link.enable: # 在新标签页中打开外部链接
post_asset_folder: # 启用资源文件夹功能
filename_case: # 将文件名转换小写小写1/大写2
relative_link: # 是否创建相对于根文件夹的链接
index_generator.per_page: # 每页显示的文章数
index_generator.order_by: # 发布顺序
date_format: # 日期格式
time_format: # 时间格式
per_page: # 每个页面上显示的文章数
pagination_dir: # 网址格式
theme: # 主题名称
theme_config: # 主题配置，覆盖主题默认值
deploy: # 部署设置
include: # 包括隐藏文件
exclude: # 排除文件/文件夹
ignore: # 忽略文件/文件夹
```

由于参数过多，只写了一部分，其他可以参考[Hexo 官方文档](https://hexo.io/docs/configuration)
**P.S.：titlecase 参数改变后部分主题可能检测不到 Categories 和 Tags 页面**

### 3.4 Particlex 主题使用说明

> 主题GitHub地址[Particlex](https://github.com/argvchs/hexo-theme-particlex).
>
> 演示地址[MCDD](http://www.ccola.xyz/)

#### 3.4.1 主题安装

进入主题目录后，克隆此仓库

```bash
git clone https://github.com/argvchs/hexo-theme-particlex.git themes\particlex
```

#### 3.4.2 关闭 Hexo 默认的 highlight

到博客根目录下的 `_config.yml`，找到 `highlight` 和 `prismjs` 参数，设置为如下：

```yaml
highlight:
    enable: false
    line_number: true
    auto_detect: false
    tab_replace: ""
    wrap: true
    hljs: false
prismjs:
    enable: false
    preprocess: true
    line_number: true
    tab_replace: ""
```

修改完请清除缓存：`hexo cl`

#### 3.4.3 头像及背景配置

```yaml
language: # Language
head_img: # Avatar URL
head_block_enable: true
home_background: # Background URL
vf_fonts_enable: false
```

其中 VF_Fonts 可变字体设置是实验性功能

#### 3.4.4 导航栏配置

为了方便，主题使用的图标是[FontAwesome 6 图标](https://fontawesome.com/search/)

```yaml
menu:
    home:
        name: house
        theme: solid
        src: /
    about:
        name: id-card
        theme: solid
        src: /about
    archives:
        name: box-archive
        theme: solid
        src: /archives
    categories:
        name: bookmark
        theme: solid
        src: /categories
    tags:
        name: tags
        theme: solid
        src: /tags
    # Example:
    # <name>:
    #     name: <icon-name>
    #     theme: <icon-theme>
    #     src: <link-url>
```

#### 3.4.5 主页信息卡片

**如果图标链接或友链为空，请在 `icon_links:` 或 `friend_links:` 后添加一个 `[]`**

```yaml
card:
    enable: true
    description: ["Description..."] # You can add more
    icon_links:
        github:
            name: github
            theme: brands
            link: https://github.com/argvchs
        # Example:
        # <name>:
        #    name: <icon-name>
        #    theme: <icon-theme>
        #    link: <link-url>
    friend_links:
        []
        # Example:
        # <name>: <link-url>
```

#### 3.4.6 首页文档缩略配置

一般来说，缩略展示文档只需要在文档中添加 `<!-- more -->` 即可，缩略内容在显示全文中也会出现

但考虑到不想把缩略内容放在正文里，就添加了此配置

配置在 Markdown 文件的 Front-Matter 中填写（被 `---` 括起来的内容），支持 Markdown 格式，不想用则不用添加

例如：（注意换行和转义 `"`）

```markdown
---
title: 
date: 2022-09-02 19:25:00
author: Cola
img: 
top: true
cover: true
coverImg: 
toc: false
description: "Cola\n**And**\n_XiaoEr_"
mathjax: false
categories: Markdown
tags:
  - Typora
  - Markdown
  - Cola
---
```

#### 3.4.7 页脚配置

考虑到博客部署在服务器并使用自己域名的情况，按国家规定需要在网站下边添加备案消息

如没有需要显示备案消息的可以关闭

```markdown
footer:
    since: 20xx
    ICP:
        enable: true
        code: 粤ICP备xxxxxx号
```

#### 3.4.8 Gitalk 评论系统

Gitalk 评论系统，默认关闭

考虑到博客可能部署到多个网站同步评论，但 OAuth APP 只能有一个回调 URL，所以添加了 `sites` 参数用于其他网站的评论，请注册多个 Oauth APP

**同样如果没有其他网站，请在 `sites:` 后添加一个 `[]`**

```yaml
gitalk:
    enable: false
    clientID: # Default ClientID
    clientSecret: # Default ClientSecret
    repo: # The name of repository of store comments
    owner: # GitHub repo owner
    admin: # GitHub repo owner and collaborators, only these guys can initialize github issues
    language: zh-CN # en, zh-CN, zh-TW, es-ES, fr, ru, de, pl and ko are currently available.
    proxy: # CORS proxy
    sites: # Sites
        []
        # Example:
        # <www.example.com>:
        #    clientID: <client-id>
        #    clientSecret: <client-secret>
```

首先，您需要选择一个公共github存储库（已存在或创建一个新的github存储库）用于存储评论

![](/20220904105442.png)

然后需要创建  **GitHub Application** ，如果没有 [点击这里申请](https://github.com/settings/applications/new)，`Authorization callback URL` 填写当前使用插件页面的域名。

![img](/20220904105312.png)

获取 Client ID 以及 Client Secret

![](/20220904105217.png)

## 四，页面渲染

### 4.1 目录介绍

介绍一下博客根目录各文件夹/文件的作用，我的主题用的是 EJS，其他如 Pug/Jade 等相差太大的模板引擎请不要参考本篇

```plaintext
<root>
|---public # 静态网页文件
|---source # 文章（不要和主题文件夹下的source弄混）
|---themes # 主题
    |---<theme-name>
        |---layout # 布局文件
        |   |---layout.ejs # 网页的基本布局
        |---source # 主题资源文件，里面的内容会生成到静态文件下
```

### 4.2 添加自定义 JS/CSS

在 `<root>\themes\<theme-name>\source` 下添加自定义文件（最好把文件放在 js、css...文件夹下分类，不然生成的静态文件会很乱），然后在 layout.ejs 下添加如下内容，如果使用网络上的文件直接在 src/href 中填写路径即可
**`<file-name>`为自定义文件名称**

```xml
<!--JS-->
<script src="/<file-name>"></script>
<!--CSS-->
<link rel="stylesheet" href="/<file-name>" />
```

将[这里](https://github.com/imuncle/live2d)的 Live2D 模型 Clone 到本地，选择一个喜❤️欢的模型（必须是 Cubism3 版本的，在 `live2d_3` 文件夹下）复制到 `<root>\themes\<theme-name>\source\model`
**`<model-name>`为模型名称**

```xml
div id="L2dCanvas"></div>
<script src="/js/live2d.min.js"></script>
<script src="/css/live2d.css"></script>
<script>
    var v = new Viewer({
        width: 240,
        height: 325,
        right: "0",
        bottom: "0",
        basePath: "/model",
        role: "<model-name>",
        mobile: true,
    });
</script>
```

### 4.3 实现流行背景，鼠标指针特效

* 下载：
    * [live2d.min.js](https://argvchs.github.io/js/live2d.min.js)
    * [live2d.css](https://argvchs.github.io/assets/live2d.css)
    * [live2d.zip](https://argvchs.github.io/assets/model.zip)（我用的 Live2d 模型）

fireworks.js：鼠标点击特效，需要前置 Anime.js

```xml
<canvas
    id="fireworks"
    style="position:fixed;top:0;left:0;width:100vw;height:100vh;pointer-events:none;z-index:2147483647"
></canvas>
<script src="/js/fireworks.js"></script>
```

* 下载：[fireworks.js](https://argvchs.github.io/js/fireworks.js)

background.js：流星背景特效

```xml
<canvas
    id="background"
    style="position:fixed;top:0;left:0;width:100vw;height:100vh;pointer-events:none;z-index:-1"
></canvas>
<script src="/js/background.js"></script>
```

* 下载：[background.js](https://argvchs.github.io/js/background.js)

cursor.js：鼠标指针特效

```xml
<div id="cursor"></div>
<script src="/css/cursor.css"></script>
<script src="/js/cursor.js"></script>
```

* [cursor.css](https://argvchs.github.io/assets/cursor.css)
* [cursor.js](https://argvchs.github.io/js/cursor.js)

### 4.4 Hexo Markdown  语法补充

Markdown 是支持渲染 HTML 的，所以可以实现各种效果
如果你要不使 HTML 标签被渲染可以在右边的小于号加 `\` 转义，如 `<tag\>`，但还是推荐 ``tag``的代码格式

* 字体
  用 `<font>` 来实现字体的样式修改
  **`<color>` `<size>` `<face>` 分别是你字体的颜色，大小和字体名称**

```markdown
<font color=<color> size=<size> face=<face>>Text...</font>
```

下载文件
Markdown 下载文件，网上搜到的都是 post_asset_folder 这个参数~（也不知道为什么我不能用）~
只要把文件放到 `<root>\theme\<theme-name>\source` 下（同样，最好分类一下），在 Markdown 中引用就行
部分文件可能不会下载，在浏览器打开，如果有洁癖可以用第二种方法
**`<file-name>`为文件名**

```markdown
[Description...](/file-name)
<a href="<file-name>" download>Description...</a>
```

* 注释
  Markdown 注释和 HTML 一样

  ```markdown
  <!-- Comment... -->markdown
  ```

  特别的，用 `<!-- more -->` 可以控制主页预览内容，后面的内容在显示全文时才出现

* 解决部分主题没有块引用的样式
  块引用会解析成 `<blockquote>` 标签，添加自定义 CSS 即可

## 五，使用 Github 搭建

### 5.1 配置 SSH 密钥

首先要有一个 [Github](https://github.com/) 账号
**`<name>` 和 `<email>` 分别是你自己的 Github 用户名和注册时使用的邮箱**
注册完成后回到主页，点击左边的绿色按钮 New，新建一个仓库，名称为 `<name>.github.io`，比如我的用户名是 argvchs，那么名称就是 argvchs.github.io，然后点击 Create repositpory 创建
在命令行输入命令 `ssh-keygen -t rsa -C "email@email.com"`，获取 SSH 密钥，这个过程会提示你输入一些东西，一直回车就行了
输入命令 `notepad %USERPROFILE%\.ssh\id_rsa.pub`，打开 SSH 密钥，先不用管，后面会用到
打开你 Github 右上角的头像中的 Settings 设置，点击左边的 SSH and GPG keys，点击右上角的 New SSH key，将刚才打开的 SSH 密钥复制到 Key 中，Title 不用写，点击 Add SSH key 添加密钥
设置好 SSH 密钥后用 `ssh -T git@github.com` 检测，如果出现 `Hi, xxx! You've successfully authenticated` 则配置成功

### 5.2 更改默认分支

打开[https://github.com/settings/repositories](https://github.com/settings/repositories)，第一个输入框就是你的默认分支，更改后点击 Update 即可
默认分支以前是 `master`，现在是 `main`，我觉得还是原来的 `master` 更好一些，网上搜到关于 Github 的文章，大部分默认分支都是 `master`
不更改也可以，但是之后修改 `_config.yml` 的参数时要将 `branch: master` 改为 `branch: main`

### 5.3 部署到 Github Pages

使用下面的命令初始配置

```bash
git config --global user.name "<name>"
git config --global user.email "<email>"bash
```

打开你博客根目录的 `_config.yml`，设置参数

```yaml
url: https://<name>.github.io/
# ...
deploy:
    type: git
    repo: git@github.com:<name>/<name>.github.io.git
    branch: master
    message:yaml
```

设置好参数，使用下面的命令安装部署插件，安装了才能部署到 Github Pages

```bash
npm i -S hexo-deployer-gitbash
```

在博客根目录下使用 `hexo d -g` 部署到 Github Pages

### 5.4 部署到 Vercel 或 Netlify 加速访问

* Vercel
  先注册一个 [Vercel](https://vercel.com/login) 账号，通过 Github 注册
  注册成功后跳转到你的首页，点击 New project，跳转后在 Import Git Repository 中选择你的 Hexo 博客，跳转后点击 Deploy 上传到 Vercel
  上传完成点击 Goto Dashboard 来到项目主页，选择顶部的 Settings，在 Project Name 中更改你网站的名称
* Netlify
  先注册一个 [Netlify](https://app.netlify.com/) 账号，通过 Github 注册
  注册成功后跳转到你的首页，点击 Add new site 中的 Import an existing project，点击 Github，与 Github 关联
  关联 Github 后在下面会出现你 Github 中的仓库，点击你创建的 Hexo 博客，再点击 Deploy site 上传
  上传完成会跳转到项目主页，选择 Site settings，跳转后往下滑，点击 Change site name 更改你网站的名称