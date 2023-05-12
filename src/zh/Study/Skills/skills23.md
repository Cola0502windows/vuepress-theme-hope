---
title: VM 虚拟机 CentOS7 安装 Vim
icon: launch
---
# VM 虚拟机 CentOS7 安装 Vim

> Author: Cola
>
> Time: 2023.02.03 20:00 PM
>
> To：VM 虚拟机 CentOS7 安装 Vim

> Features:
>
> - [ ] 结构
> - [ ] 上传 DOC

## 一、vim的介绍

- vim是一个功能强大的全屏幕文本编辑器，是linux/unix上最常用的文本编辑器
- 它的作用是建立、编辑、显示文本文件
- vim没有菜单，只有命令

## 二、安装VIM编辑器

> 使用命令 `yum -y install vim*` 进行安装即可

### 三、配置 Vim

> 打开配置文件 `vim /etc/vimrc`

```xml
set nu          " 设置显示行号
 set showmode    " 设置在命令行界面最下面显示当前模式等
 set ruler       " 在右下角显示光标所在的行数等信息
 set autoindent  " 设置每次单击Enter键后，光标移动到下一行时与上一行的起始字符对齐
 syntax on       " 即设置语法检测，当编辑C或者Shell脚本时，关键字会用特殊颜色显示
```

## 四、Vim 常用模式和命令

> 1. 命令模式
> 2. 插入模式
> 3. 编辑模式

![image-20230203201958686](/image-20230203201958686.png)

