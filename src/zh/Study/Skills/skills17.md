---
title: 初始化 VuePress Theme Hope 
icon: launch
---
> Author: Cola  
> Time: 2022/12/17 18:23  
> To: 初始化 VuePress Theme Hope 

> Features:
>
> - [x] 结构
> - [ ] 上传 DOC

# 初始化 VuePress Theme Hope 

> VuePress Theme Hope 是一个具有强大功能的 vuepress 主题✨
>
> - [官网]([主页 | vuepress-theme-hope (vuejs.press)](https://theme-hope.vuejs.press/zh/))

> Features:
>
> - [ ] 环境准备
> - [ ] 参数配置

## 一、环境准备

> Features:
>
> - [ ] 安装 node
> - [ ] 安装 pnpm
> - [ ] 初始化项目

### 1.1 安装 node

> 官方推荐使用[Node 18.12.1](https://nodejs.org/download/release/v18.12.1/) 进行安装

### 1.2 安装 pnpm

> 注意：使用管理员模式打开 Terminal 终端：
>
> - `corepack enable`
> - `corepack prepare pnpm@7.24.3 --activate`

![image-20230204171219301](/image-20230204171219301.png)

### 1.3 初始化项目

> 创建项目文件夹后进入终端：
>
> - `pnpm create vuepress-theme-hope my-docs`

![image-20230204171200889](/image-20230204171200889.png)

![image-20230204171420809](/image-20230204171420809.png)

### 1.4 项目目录介绍

VuePress 是以 Markdown 为中心的。你项目中的每一个 Markdown 文件都是一个单独的页面。

默认情况下，页面的路由路径是根据你的 Markdown 文件的相对路径决定的。

由于你的项目是通过创建助手生成的，那么你会得到以下文件结构:

```xml
└─ docs
   ├─ guide
   │  ├─ ...
   │  └─ page.md
   │  └─ markdown.md
   │  └─ README.md
   ├─ ...
   ├─ slide.md
   └─ README.md
```

你的 Markdown 文件对应的路由路径为:

| 相对路径           | 路由路径            |
| ------------------ | ------------------- |
| `/README.md`       | `/`                 |
| `/slide.md`        | `/slide.html`       |
| `/guide/README.md` | `/guide/`           |
| `/guide/slide.md`  | `/guide/slide.html` |
| `/guide/page.md`   | `/guide/page.html`  |

------

> `README.md` 是特例，在 Markdown 中，按照约定俗成，它会作为所在文件夹的主页。所以在渲染为网页时，它的对应路径为网页中的主页路径 `index.html`。

> .
> ├── .github (可选的) → GitHub 配置文件存放路径
> │    └── workflow → GitHub 工作流配置
> │         └── docs-deploy.yml → 自动部署文档的工作流
> |
> ├── src → 文档文件夹
> │    │
> │    ├── .vuepress (可选的) → VuePress 配置文件夹
> │    │    │
> │    │    ├── dist (默认的) → 构建输出目录
> │    │    │
> │    │    ├── public (可选的) → 静态资源目录
> │    │    │
> │    │    ├── styles (可选的) → 用于存放样式相关的文件
> │    │    │
> │    │    ├── config.{js,ts} (可选的) → 配置文件的入口文件
> │    │    │
> │    │    └── client.{js,ts} (可选的) → 客户端文件
> │    │
> │    ├── ... → 其他项目文档
> │    │
> │    └── README.md → 项目主页
> │
> └── package.json → Nodejs 配置文件

### 1.5 启动项目

> - `pnpm docs:dev` 启动开发服务器
> - `pnpm docs:build` 构建项目并输出
> - `pnpm docs:clean-dev` 清除缓存并启动开发服务器

> 如需指定端口：
>
> 可进入` package.json` 所在目录中使用 `npm run docs:dev -- --port [端口]` 进行启动

![image-20230204175102833](/image-20230204175102833.png)

![image-20230204175122022](/image-20230204175122022.png)

## 二、 参数配置

> Features:
>
> - [ ] 常用参数配置
> - [ ] 配置评论

### 2.1 常用参数配置

> - [x] Frontmatter

#### 2.1.1 Frontmatter

Frontmatter 是 VuePress 中很重要的一个概念，它用于承载 Markdown 文件的配置。

Frontmatter 必须在 Markdown 文件的顶部，并且被包裹在一对三短划线中间。下面是一个基本的示例:

```markdown
---
lang: zh-CN
title: 页面的标题
description: 页面的描述
---

<!-- 这里是 Markdown 内容 -->

...
```

你肯定注意到 Frontmatter 中的字段和 VuePress 配置文件十分类似。你可以通过 Frontmatter 来覆盖当前页面的 `lang`, `title`, `description` 等属性。因此，你可以把 Frontmatter 当作页面级作用域的配置，它通常具有最高优先级，所作配置仅对当前页面生效。

### 2.2 配置评论
