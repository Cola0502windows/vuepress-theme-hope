---
title: IDEA 使用技巧和常用插件
icon: launch
---

# IDEA 使用技巧和常用插件

> Author: Cola
>
> Time: 2023.02.03 19.58 PM
>
> To：IDEA 使用技巧和常用插件

> Features:
>
> - [X] 结构
> - [x] 上传 DOC


## 一、IDEA 使用技巧

> * [x] IDEA 常用快捷键
> * [ ] 通用配置
> * [ ] 常见工程的创建

### 1.1 IDEA 常用快捷键

#### 1.1.1 通用型

| 说明         | 快捷键                                    |
| ------------ | ----------------------------------------- |
| **复制代码** | **<kbd>Ctrl</kbd> + C**                   |
| **粘贴**     | **<kbd>Ctrl</kbd> + V**                   |
| **剪切**     | **<kbd>Ctrl</kbd> + X**                   |
| **撤销**     | **<kbd>Ctrl</kbd> + Z**                   |
| **反撤销**   | **<kbd>Ctrl</kbd> + <kbd>Shift</kbd> +C** |
| **保存**     | **<kbd>Ctrl</kbd> + S**                   |
| **全选**     | **<kbd>Ctrl</kbd> + A**                   |

#### 1.1.2 调整格式

| 说明                   | 快捷键                                     |
| ---------------------- | ------------------------------------------ |
| **格式化代码**         | **<kbd>Ctrl</kbd> + <kbd>Alt</kbd> + L**   |
| **使用单行注释**       | **<kbd>Ctrl</kbd> + /**                    |
| **使用/取消多行注释**  | **<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + /** |
| 选中数行，整体往后移动 | <kbd>TAB</kbd>                             |
| 选中数行，整体往前移动 | <kbd>Shift</kbd> + <kbd>TAB</kbd>          |

#### 1.1.3 提高编写速度

| 说明                                   | 快捷键                                            |
| -------------------------------------- | ------------------------------------------------- |
| **智能提示**                           | **<kbd>Alt</kbd> + <kbd>Enter</kbd>**             |
| 提示代码模板                           | <kbd>Ctrl</kbd>+ J                                |
| 使用xx块环绕                           | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+ T                 |
| **调出生成getter/setter/构造器等结构** | **<kbd>Alt</kbd>+ <kbd>Insert</kbd>**             |
| **自动生成返回值变量**                 | **<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+ V**             |
| **复制指定行的代码**                   | **<kbd>Ctrl</kbd>+ D**                            |
| 删除指定行的代码                       | <kbd>Ctrl</kbd>+ Y                                |
| 切换到下一行代码空位                   | <kbd>Shift</kbd> + <kbd>Enter</kbd>               |
| 切换到上一行代码空位                   | <kbd>Ctrl</kbd> +<kbd>Alt</kbd>+ <kbd>Enter</kbd> |
| 向上移动代码                           | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>↑</kbd>     |
| 向下移动代码                           | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>↓</kbd>     |
| 向上移动一行                           | <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>↑</kbd>      |
| 向下移动一行                           | <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>↓</kbd>      |
| **方法的形参列表提醒**                 | **<kbd>Ctrl</kbd>+ P**                            |
| 批量修改指定的变量名、方法名、类名等   | <kbd>Shift</kbd>+<kbd>F6</kbd>                    |
| **抽取代码重构方法**                   | **<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+ M**             |
| **重写父类的方法**                     | **<kbd>Ctrl</kbd>+ O**                            |
| **实现接口的方法**                     | **<kbd>Ctrl</kbd>+ I**                            |
| 选中的结构的大小写的切换               | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+ U               |
| **批量导包**                           | **<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+ O**             |



#### 1.1.4 类结构、查找和查看源码

| 说明                                       | 快捷键                                                 |
| ------------------------------------------ | ------------------------------------------------------ |
| 如何查看源码                               | <kbd>Ctrl</kbd> + 选中指定的结构 或 <kbd>Ctrl</kbd>+ N |
| 显示当前类结构，支持搜索指定的方法、属性等 | <kbd>Ctrl</kbd>+<kbd>F12</kbd>                         |
| 退回到前一个编辑的页面                     | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+←                       |
| 进入到下一个编辑的页面                     | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+→                       |
| 打开的类文件之间切换                       | <kbd>Alt</kbd>+←/→                                     |
| 光标选中指定的类，查看继承树结构           | <kbd>Ctrl</kbd>+ <kbd>H</kbd>                          |
| 查看方法文档                               | <kbd>Ctrl</kbd>+<kbd>Q</kbd>                           |
| 类的UML关系图                              | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+ <kbd>U</kbd>           |
| 定位某行                                   | <kbd>Ctrl</kbd>+<kbd>G</kbd>                           |
| 回溯变量或方法的来源                       | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>B</kbd>            |
| **折叠方法实现**                           | **<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+ <kbd>-</kbd>**     |
| **展开方法实现**                           | **<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+ <kbd>+</kbd>**     |

#### 1.1.5 查找、替换与关闭

| 说明                                               | 快捷键                              |
| -------------------------------------------------- | ----------------------------------- |
| 查找指定的结构                                     | ctlr+ F                             |
| 快速查找：选中的Word快速定位到下一个               | <kbd>Ctrl</kbd>+ l                  |
| 查找与替换                                         | <kbd>Ctrl</kbd>+ R                  |
| 直接定位到当前行的首位                             | <kbd>Home</kbd>                     |
| 直接定位到当前行的末位                             | <kbd>End</kbd>                      |
| 查询当前元素在当前文件中的引用，然后按 F3 可以选择 | <kbd>Ctrl</kbd>+ <kbd>F7</kbd>      |
| 全项目搜索文本                                     | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+ F |
| 关闭当前窗口                                       | <kbd>Ctrl</kbd>+<kbd>F4</kbd>       |

> 可以使用正则表达式对需要查找或替换的内容进行匹配，后搭配 <kbd> Shift </kbd>+ <kbd>↓</kbd> 或 <kbd>↑</kbd> 进行多光标批量修改。

#### 1.1.6 Debug快捷键

| 说明                                 | 快捷键                                           |
| ------------------------------------ | ------------------------------------------------ |
| 单步调试（进入函数内部）             | <kbd>F7</kbd>                                    |
| 单步调试（不进入函数内部）           | <kbd>F8</kbd>                                    |
| 强制单步调试（进入函数内部）         | <kbd>Alt</kbd> +<kbd>Shift</kbd> +<kbd>F7</kbd>  |
| 选择要进入的函数                     | <kbd>Shift</kbd>  + <kbd>F7</kbd>                |
| 跳出函数                             | <kbd>Shift</kbd> + <kbd>F8 </kbd>                |
| 运行到断点                           | <kbd>Alt</kbd>  + <kbd>F9 </kbd>                 |
| 继续执行，进入下一个断点或执行完程序 | <kbd>F9</kbd>                                    |
| 停止                                 | <kbd>Ctrl</kbd> +<kbd>F2</kbd>                   |
| 查看断点                             | <kbd>Ctrl</kbd> +<kbd>Shift</kbd> +<kbd>F8</kbd> |
| 关闭                                 | <kbd>Ctrl</kbd> +<kbd>F4</kbd>                   |

### 1.2 通用配置

> 通用配置

### 1.3 常见工程的创建

> - [ ] 普通 Java 工程
> - [ ] Maven 工程
> - [ ] SpringBoot 工程

#### 1.3.1 普通 Java 工程

> 普通 Java 工程

#### 1.3.2 Maven 工程

> Maven 工程

#### 1.3.3 SpringBoot 工程

> SpringBoot 工程

### 二、IDEA 常用插件

> - [x] 功能
> - [x] 美化

### 2.1 功能

> 功能

### 2.2 美化

> 美化
