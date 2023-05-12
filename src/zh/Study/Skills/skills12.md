---
title: Microsoft Store 报网络连接错误解决方法
icon: launch
---
# Microsoft Store 报网络连接错误解决方法

> Author: Cola
>
> Time: 2022.11.08 15.45
>
> To：Microsoft Store 报网络连接错误解决方法

> Features:
>
> - [X] 解决 Windows OS 下开启系统代理导致Microsoft Store 等 UWP 应用无法联网。

> 错误提示：
>
> 原因：Windows OS 下开启系统代理导致Microsoft Store 等 UWP 应用无法联网。

![1667959436950](/1667959436950.png)

以管理员方式打开 `Powershell` 输入

```powershell
foreach ($n in (get-appxpackage).packagefamilyname) {checknetisolation loopbackexempt -a -n="$n"}
```

若出现，使用网络代理无法上谷歌等外网，恢复命令：

```powershell
foreach ($n in (get-appxpackage).packagefamilyname) {checknetisolation loopbackexempt -d -n="$n"}
```
