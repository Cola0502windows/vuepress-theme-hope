---
title: MySQL 数据库设计三大规范
icon: ask
---

# MySQL 数据库设计三大规范

> Author：Cola
>
> Time：2023.1.30 15：24 PM
>
> To：学习笔记之 MySQL 数据库设计的三大规范

## Features

> - [ ] 基本结构
> - [ ] 上传 DOC

## 一、 MySQL 中数据库设计三大规范

> - [ ] FN 1 
> - [ ] FN 2 
> - [ ]  FN 3 

### 1.1 FN 1 

> 范式一：表格存储结构中，每一个行列交叉点遵循一个原子性（不能继续拆）为了保持数据的查询效率，通常要求每一个表格中有索引列，该索引可以是：
>
> - 主键
> - 联合主键

例如下表就可以采用 `联合主键` （工程编号 + 工程师编号）进行索引的构建，使其遵循 FN 1

| 工程编号 | 工程名 | 工程师编号 | 工程师名 | 职称 | 薪资 |
| :------: | ------ | ---------- | -------- | ---- | ---- |
|    A     | 汾阳   | 1          | Cola     | 普通 | 100  |
|    A     | 汾阳   | 2          | RHF      | 中级 | 200  |
|    B     | 晋中   | 1          | Cola     | 普通 | 100  |
|    B     | 晋中   | 3          | RH       | 高级 | 300  |
|    C     | 晋城   | 2          | RHF      | 中级 | 200  |
|    C     | 晋城   | 3          | RH       | 高级 | 300  |

### 1.2 FN 2

> 范式二：是在遵循范式一的基础上，保证表格内没有部分依赖性即非主键列不能受主键列的影响。

在 `FN 1` 中的表中我们将 `工程编号` 和 `工程师编号` 组合为联合主键，但这个时候非主键列 `工程师名` 和 部分主键（工程师编号）存在依赖关系，因此我们需要将上表改造为：

> - 工程师表
> - 工程表

#### 1.2.1 工程师表

| 工程师编号 （PK） | 工程师名 |
| ----------------- | -------- |
| 1                 | Cola     |
| 2                 | RHF      |
| 3                 | RH       |

#### 1.2.2 工程表

| 工程编号 | 工程名 |职称 | 薪资 |
| :------: | ------| ---- | ---- |
|    A     | 汾阳   | 普通 | 100  |
|    A     | 汾阳  | 中级 | 200  |
|    B     | 晋中  | 普通 | 100  |
|    B     | 晋中  | 高级 | 300  |
|    C     | 晋城   | 中级 | 200  |
|    C     | 晋城  | 高级 | 300  |

### 1.3 FN 3 

> 范式三：在遵循 FN 1 和 FN 2 的基础上，还要求表格内不允许出现传递依赖项（非主键列不能收到主键列的影响）

在 `FN 2` 中为了避免非主键列受到部分主键列的影响我们将原有的表格拆分为：

- 工程师表
- 工程表

但这样在工程师表中非主键列 职称和薪资 仍受 非主键列 工程名的影响，因此我们需要将 `FN 2` 中的工程师表拆分为：

- 职称表
- 工程表

#### 1.3.1 职称表

| 职称编号（PK） | 职称 | 薪资 |
| -------------- | ---- | ---- |
| 1              | 普通 | 100  |
| 2              | 中级 | 200  |
| 3              | 高级 | 300  |

#### 1.3.2 工程表

| 工程编号 | 工程名 |
| :------: | ------ |
|    A     | 汾阳   |
|    B     | 晋中   |
|    C     | 晋城   |

## 二、总结

> 经过上述过程的改造，我们已经将 FN 1 中的表格拆分为：
>
> - 工程师表
> - 职称表
> - 工程表

### 2.1 工程师表

> 工程师表与职称表为一对多关系，因此我们可以在工程师表中添加外键：

| 工程师编号 （PK） | 工程师名 | 外键 |
| ----------------- | -------- | ---- |
| 1                 | Cola     | 1    |
| 2                 | RHF      | 2    |
| 3                 | RH       | 3    |

### 2.2 职称表

| 职称编号（PK） | 职称 | 薪资 |
| -------------- | ---- | ---- |
| 1              | 普通 | 100  |
| 2              | 中级 | 200  |
| 3              | 高级 | 300  |

### 2.3 工程表

| 工程编号 | 工程名 |
| :------: | ------ |
|    A     | 汾阳   |
|    B     | 晋中   |
|    C     | 晋城   |

> 工程表与工程师表为多对多关系，因此我们可以添加 `工程_工程师表` 来维护二者的关系：

#### 2.3.1 工程_工程师表

| 工程 | 工程师 |
| ---- | ------ |
| A    | 1      |
| A    | 2      |
| B    | 1      |
| B    | 3      |
| C    | 2      |
| C    | 3      |

