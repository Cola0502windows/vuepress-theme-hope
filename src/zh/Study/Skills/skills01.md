---
title: Markdown 使用技巧
icon: launch
order: 1
---


# Markdown 使用技巧

> Author: Cola
>
> Time: 2022.11.08 15.45
>
> To：记录 常用的 Markdown 语法

> Features:
>
> - [X] 完善基本语法的使用
> - [ ] 添加数学公式、时序图等的使用
> - [ ] 记录相关软件的使用  Typora 和 Obsidian
> - [X] 使用GitHub和PicGo搭建图床
> - [ ] 通过 `<a> 和 <img> 标签 `实现文件的下载
> - [x] 中文编码

## Markdown 概述

![](/1665028181585-image.png)

> - Markdown 是一种轻量级标记语言，它允许人们使用易读易写的纯文本格式编写文档。
> - Markdown 语言在 2004 由约翰·格鲁伯（英语：John Gruber）创建。
> - Markdown 编写的文档可以导出 HTML 、Word、图像、PDF、Epub 等多种格式的文档。
> - Markdown 编写的文档后缀为 **.md**, **.markdown**

[Markdown官方中文文档](https://markdown.com.cn/) ✍️

## 基本语法

### Markdown 标题

> **Markdown 标题有两种格式:**
>
> * **使用 = 和 - 标记一级和二级标题**
> * **使用 # 号标记多级标题**

- 使用 = 和 - 标记一级和二级标题

```markdown
一级标题
=======
二级标题
-------
```

![image.png](/1665028721919-image.png)

- 使用 # 号标记多级标题

```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```

![image.png](/1665028739780-image.png)

### Markdown 段落格式

> Markdown 段落没有特殊的格式，直接编写文字就好， **段落的换行是使用两个以上空格加上回车或使用空行进行换行** 。

- 使用两个以上空格加回车实现换行

![image.png](/1665028949584-image.png)

- 使用空行进行换行

![image.png](/1665028971488-image.png)

> Markdown 可以使用以下几种字体：

```
*斜体文本*
_斜体文本_
**粗体文本**
__粗体文本__
***粗斜体文本***
___粗斜体文本___
```

![image.png](/1665029024765-image.png)

> 你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：

```
***

* * *

*****

- - -

----------
```

![image.png](/1665029085300-image.png)

> 如果段落上的文字要添加删除线，只需要在文字的两端加上两个波浪线 **~~** 即可，实例如下：

```markdown
删除线
~~删除线~~
```

![image.png](/1665029147194-image.png)

> 下划线可以通过 HTML 的 **`<u>`** 标签来实现：

```
<u>带下划线文本</u>
```

![image.png](/1665029181519-image.png)

> 脚注是对文本的补充说明。
>
> Markdown 脚注的格式如下:

```
这是一个脚注:[^Cola]
[^Cola]: ColaAndXiaoEr
```

![image.png](/1665029301967-image.png)

### Markdown 列表

> Markdown 支持有序列表和无序列表。
>
> 无序列表使用星号(*)、加号(+)或是减号(-)作为列表标记，这些标记后面要添加一个空格，然后再填写内容：

```
* 第一项
* 第二项
* 第三项

+ 第一项
+ 第二项
+ 第三项


- 第一项
- 第二项
- 第三项
```

![image.png](/1665029412941-image.png)

> 有序列表使用数字并加上 **.** 号来表示，如：

```
1. 第一项
2. 第二项
3. 第三项
```

![image.png](/1665029441854-image.png)

> 列表嵌套只需在子列表中的选项前面添加两个或四个空格即可：

```
1. 第一项：
    - 第一项嵌套的第一个元素
    - 第一项嵌套的第二个元素
2. 第二项：
    - 第二项嵌套的第一个元素
    - 第二项嵌套的第二个元素
```

![image.png](/1665029473260-image.png)

### Markdown 区块

> Markdown 区块引用是在段落开头使用 **>** 符号 ，然后后面紧跟一个**空格**符号：

```
> 区块引用
> Cola
> XiaoEr
```

![image.png](/1665029609093-image.png)

> 外区块是可以嵌套的，一个 **>** 符号是最外层，两个 **>** 符号是第一层嵌套，以此类推：

```
> 最外层
> > 第一层嵌套
> > > 第二层嵌套
```

![image.png](/1665029634641-image.png)

> 区块中使用列表实例如下：

```
> 区块中使用列表
> 1. 第一项
> 2. 第二项
> + 第一项
> + 第二项
> + 第三项
```

![image.png](/1665029664349-image.png)

> 如果要在列表项目内放进区块，那么就需要在 **>** 前添加四个空格的缩进。
>
> 列表中使用区块实例如下：

```
* 第一项
    > Cola
    > ColaAndXiaoEr
* 第二项
```

![image.png](/1665029873865-image.png)

### Markdown 代码

> 如果是段落上的一个函数或片段的代码可以用反引号把它包起来（**`**），例如：

```
`printf()`函数
```

![image.png](/1665029946845-image.png)

> 代码区块使用 3 个反引号

```javascript
$(document).ready(function () {
    alert('ColaAndXiaoEr');
});
```

![image.png](/1665030030885-image.png)

![image.png](/1665030067580-image.png)

### Markdown 链接

> 链接使用方法如下：

```
[链接名称](链接地址)

或者

<链接地址>
```

```
这是一个链接[ColaBlog](http://www.ccola.xyz/)
```

![image.png](/1665030209555-image.png)

> 我们可以通过变量来设置一个链接，变量赋值在文档末尾进行：

```
这个链接用 google 作为网址变量 [Google官网][google]
这个链接用 colablog 作为网址变量 [ColaBlog][colablog]
然后在文档的结尾为变量赋值（网址）

  [google]: http://www.google.com/
  [colablog]: http://www.ccola.xyz/
```

### Markdown 图片

> Markdown 图片语法格式如下：

```
![alt 属性文本](图片地址)

![alt 属性文本](图片地址 "可选标题")
```

* 开头一个感叹号 !
* 接着一个方括号，里面放上图片的替代文字
* 接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上选择性的 'title' 属性的文字。

```markdown
![DaoMei](https://raw.githubusercontent.com/1203952894/cloudimg/main/DaoMei_20220927184644.png "刀妹")
```

![image.png](/1665030536995-image.png)

> Markdown 还没有办法指定图片的高度与宽度，如果你需要的话，你可以使用普通的 `<img>` 标签。

```
<img src="https:E:/docsify/ColaJava/docs/asset//raw.githubusercontent.com/1203952894/cloudimg/main/DaoMei_20220927184644.png" width="50%">
```

![image.png](/1665030666759-image.png)

### Markdown 表格

> Markdown 制作表格使用 **|** 来分隔不同的单元格，使用 **-** 来分隔表头和其他行。
>
> 语法格式如下：

```
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |
```

![image.png](/1665030804058-image.png)

> **我们可以设置表格的对齐方式：**
>
> * **-:** 设置内容和标题栏居右对齐。
> * **:-** 设置内容和标题栏居左对齐。
> * **:-:** 设置内容和标题栏居中对齐。

```
| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 |
```

![image.png](/1665030853786-image.png)

### Markdown 拓展元素

> 不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。
>
> 目前支持的 HTML 元素有：`<kbd> <b> <i> <em> <sup> <sub> <br>`等 ，如：

> 显示按键

```
使用<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd>重启电脑
```

![image.png](/1665030921715-image.png)

#### Markdown 任务列表

> 任务列表使您可以创建带有复选框的项目列表。

```markdown
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media
```

![imgae](/1667895784304.png)

#### Video 图片标签

> 你可以使用 `<video>` HTML 标签来插入视频，例如 `<video controls='controls 'src=".mp4"> </video>`

<video  controls="controls" src="/videos/video.mp4" > </video>

#### Audio 音乐标签

> 你可以使用 `<audio>` HTML 标签来插入音乐，例如 `<audio  controls='controls ' src=".mp3"> </audio>`

<audio  controls="controls" src="/musics/music.mp3"> </audio>

#### TOC 快速实现目录

> 我们可以使用 `[TOC] 来快速实现目录结构`

[toc]

## 扩展语法

## 插件

### 使用 GitHub + picGo 搭建图床

#### 1. 概述

**什么是图床:**

> 图床指的是存储图片的服务器

**为什么使用图床：**

> 1. 使用图床可以方便对图片的统一处理

2. 不存在因电脑硬盘损坏导致图片丢失的问题
3. 使用Typora等MarkDown文档编写也会很方便

#### 2. 搭建步骤

##### 2.1 配置 GitHub

- 首先你需要一个GitHub账号 **注册地址:**[GitHub](https://github.com/)
- 注册好后登录，然后单机右上角 ➕ 处 创建一个新仓库用于存储图片
  ![新建仓库](/20220809154418.png)
- 填写仓库名和描述(仓库名必须是public的否则存储的图片不能正常访问)
  ![描述信息](/20220809154826.png)
- 生成一个token(令牌),用于后续picGo访问GitHub
  ![主页token入口](/20220809155102.png)
  ![token](/20220809155144.png)
  **注意：** 此处token只会在此处出现注意保存

##### 2.2 下载picGo

- 访问[picGo官网](https://github.com/Molunerfinn/PicGo/releases)根据自己系统选择对应版本下载安装
- 配置picGo![picGo](/20220809155438.png)

  > 1. 此处仓库名即为 刚才设置的名称 (标准格式为 用户名/仓库名)
  >

    2. 分支名为 main (GitHub的分支名)
    3. token （刚才生成的token）
    4. 存储路径 （默认为 img/ 即可）
    5. 自定义域名 （即为上传成功后生成的url 标准格式为 https://raw.githubusercontent.com/用户名/仓库名/分支名）
- 设置上传快捷键
  ![快捷键](/20220809155942.png)

##### 2.3 配置Typora

- 配置图片上传服务
  ![图片上传服务](/20220809160102.png)

#### 测试

- 截取图片后 使用快捷键进行上传
  ![](/20220809160334.png)
- 成功后即可获得该图片的 url 直接粘贴即可
  ![](/20220809160504.png)

### 中文文案排版指北

> [GitHub 官方主页](https://github.com/sparanoid/chinese-copywriting-guidelines/blob/master/README.zh-Hans.md) 😶‍🌫️

> 设置：

![image-20221113212538239](/image-20221113212538239.png)

---

#### 空格

> 「有研究显示，打字的时候不喜欢在中文和英文之间加空格的人，感情路都走得很辛苦，有七成的比例会在 34 岁的时候跟自己不爱的人结婚，而其余三成的人最后只能把遗产留给自己的猫。毕竟爱情跟书写都需要适时地留白。
>
> 与大家共勉之。」——[vinta/paranoid-auto-spacing](https://github.com/vinta/pangu.js)

##### 中英文之间需要增加空格

正确：

> 在 LeanCloud 上，数据存储是围绕 `AVObject` 进行的。

错误：

> 在LeanCloud上，数据存储是围绕 `AVObject`进行的。
>
> 在 LeanCloud上，数据存储是围绕 `AVObject` 进行的。

完整的正确用法：

> 在 LeanCloud 上，数据存储是围绕 `AVObject` 进行的。每个 `AVObject` 都包含了与 JSON 兼容的 key-value 对应的数据。数据是 schema-free 的，你不需要在每个 `AVObject` 上提前指定存在哪些键，只要直接设定对应的 key-value 即可。

例外：「豆瓣FM」等产品名词，按照官方所定义的格式书写。

##### 中文与数字之间需要增加空格

正确：

> 今天出去买菜花了 5000 元。

错误：

> 今天出去买菜花了 5000元。
>
> 今天出去买菜花了5000元。

##### 数字与单位之间需要增加空格

正确：

> 我家的光纤入屋宽带有 10 Gbps，SSD 一共有 20 TB

错误：

> 我家的光纤入屋宽带有 10Gbps，SSD 一共有 20TB

例外：度数／百分比与数字之间不需要增加空格：

正确：

> 角度为 90° 的角，就是直角。
>
> 新 MacBook Pro 有 15% 的 CPU 性能提升。

错误：

> 角度为 90 ° 的角，就是直角。
>
> 新 MacBook Pro 有 15 % 的 CPU 性能提升。

##### 全角标点与其他字符之间不加空格

正确：

> 刚刚买了一部 iPhone，好开心！

错误：

> 刚刚买了一部 iPhone ，好开心！
>
> 刚刚买了一部 iPhone， 好开心！

##### 用 `text-spacing` 来挽救？

CSS Text Module Level 4 的 [`text-spacing`](https://www.w3.org/TR/css-text-4/#text-spacing-property) 和 Microsoft 的 [`-ms-text-autospace`](https://msdn.microsoft.com/library/ms531164(v=vs.85).aspx) 可以实现自动为中英文之间增加空白。不过目前并未普及，另外在其他应用场景，例如 macOS、iOS、Windows 等用户界面目前并不存在这个特性，所以请继续保持随手加空格的习惯。

#### 标点符号

##### 不重复使用标点符号

即使中国大陆的标点符号用法允许重复使用标点符号，但是这么做会破坏句子的美观性。

正确：

> 德国队竟然战胜了巴西队！
>
> 她竟然对你说「喵」？！

错误：

> 德国队竟然战胜了巴西队！！
>
> 德国队竟然战胜了巴西队！！！！！！！！
>
> 她竟然对你说「喵」？？！！
>
> 她竟然对你说「喵」？！？！？？！！

#### 全角和半角

不明白什么是全角（全形）与半角（半形）符号？请查看维基百科条目『[全角和半角](https://zh.wikipedia.org/wiki/%E5%85%A8%E5%BD%A2%E5%92%8C%E5%8D%8A%E5%BD%A2)』。

##### 使用全角中文标点

正确：

> 嗨！你知道嘛？今天前台的小妹跟我说「喵」了哎！
>
> 核磁共振成像（NMRI）是什么原理都不知道？JFGI！

错误：

> 嗨! 你知道嘛? 今天前台的小妹跟我说 "喵" 了哎！
>
> 嗨!你知道嘛?今天前台的小妹跟我说"喵"了哎！
>
> 核磁共振成像 (NMRI) 是什么原理都不知道? JFGI!
>
> 核磁共振成像(NMRI)是什么原理都不知道?JFGI!

##### 数字使用半角字符

正确：

> 这个蛋糕只卖 1000 元。

错误：

> 这个蛋糕只卖 １０００ 元。

例外：在设计稿、宣传海报中如出现极少量数字的情形时，为方便文字对齐，是可以使用全角数字的。

##### 遇到完整的英文整句、特殊名词，其内容使用半角标点

正确：

> 乔布斯那句话是怎么说的？「Stay hungry, stay foolish.」
>
> 推荐你阅读《Hackers & Painters: Big Ideas from the Computer Age》，非常的有趣。

错误：

> 乔布斯那句话是怎么说的？「Stay hungry，stay foolish。」
>
> 推荐你阅读《Hackers＆Painters：Big Ideas from the Computer Age》，非常的有趣。

#### 名词

##### 专有名词使用正确的大小写

大小写相关用法原属于英文书写范畴，不属于本 wiki 讨论内容，在这里只对部分易错用法进行简述。

正确：

> 使用 GitHub 登录
>
> 我们的客户有 GitHub、Foursquare、Microsoft Corporation、Google、Facebook, Inc.。

错误：

> 使用 github 登录
>
> 使用 GITHUB 登录
>
> 使用 Github 登录
>
> 使用 gitHub 登录
>
> 使用 gｲんĤЦ8 登录
>
> 我们的客户有 github、foursquare、microsoft corporation、google、facebook, inc.。
>
> 我们的客户有 GITHUB、FOURSQUARE、MICROSOFT CORPORATION、GOOGLE、FACEBOOK, INC.。
>
> 我们的客户有 Github、FourSquare、MicroSoft Corporation、Google、FaceBook, Inc.。
>
> 我们的客户有 gitHub、fourSquare、microSoft Corporation、google、faceBook, Inc.。
>
> 我们的客户有 gｲんĤЦ8、ｷouЯƧquﾑгє、๓เςг๏ร๏Ŧt ς๏гק๏гคtเ๏ภn、900913、ƒ4ᄃëв๏๏к, IПᄃ.。

注意：当网页中需要配合整体视觉风格而出现全部大写／小写的情形，HTML 中请使用标淮的大小写规范进行书写；并通过 `text-transform: uppercase;`／`text-transform: lowercase;` 对表现形式进行定义。

##### 不要使用不地道的缩写

正确：

> 我们需要一位熟悉 TypeScript、HTML5，至少理解一种框架（如 React、Next.js）的前端开发者。

错误：

> 我们需要一位熟悉 Ts、h5，至少理解一种框架（如 RJS、nextjs）的 FED。

#### 争议

以下用法略带有个人色彩，即：无论是否遵循下述规则，从语法的角度来讲都是**正确**的。

##### 链接之间增加空格

用法：

> 请 [提交一个 issue](#) 并分配给相关同事。
>
> 访问我们网站的最新动态，请 [点击这里](#) 进行订阅！

对比用法：

> 请[提交一个 issue](#)并分配给相关同事。
>
> 访问我们网站的最新动态，请[点击这里](#)进行订阅！

##### 简体中文使用直角引号

用法：

> 「老师，『有条不紊』的『紊』是什么意思？」

对比用法：

> “老师，‘有条不紊’的‘紊’是什么意思？”
