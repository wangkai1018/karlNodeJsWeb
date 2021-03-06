---
title: android系统特性与平台架构
date: 2015-09-08 11:47:43
tags:
- android
---

### 1.应用程序框架支持组件的重用与替换（app发布的时候遵守了框架的约定，其他APP也可以使用该模块）

### 2.`Dalvik`虚拟机：专门为移动设备优化；集成的浏览器：`webkit`引擎

### 3.`sqlite`结构化的数据存储

### 4.优化的图形库，多媒体支持，`GSM`电话技术，蓝牙等

### 5.采用软件叠层方式构建

****


# android平台架构：
### 1.`application`：应用程序层，我们平时做的开发就是在这个层次上进行的，包括一些内置的应用程序，使用的是java语言。

### 2.`application framework`:应用程序框架层，无论内置还是我们自己编写的app都是使用的这个层，比如我们实现一个来电黑名单，自动挂断电话，我们就需要用到电话管理（`telephonyManager`）通过该层，我们就可以很轻松的实现挂断操作，而不需要关心底层实现

### 3.`libraries`(库)+android Runtime(android运行时)：android提供了一些c和c++库，为不同组件所使用，比如媒体框架。android运行时则由android核心库集+Dalvik虚拟机构成，Dalvik虚拟机是针对 移动设备的虚拟机，它的特点：不需要很快的CPU计算速度和大量的内存空间；而每个app都单独地运行在单独的Dalvik虚拟机内每个app对应一个Dalvik集成。通过DX工具------将class文件打包------编译-----.dex文件-----Dalvik则运行.dex文件


### 4.`linux`内核  这里就是涉及底层驱动的东西了，一些系统服务，比如安全性，内存管理以及进程管理等。

---

# 相关术语的解析：

### 1.Dalvik:android特有的虚拟机，和JVM不同，Dalvik非常适合在移动终端上使用。

### 2.`AVD`：android虚拟设备，模拟器

### 3.`SDK`：软件开发工具包，就是安卓系统、平台架构的工具集合，如adb.exe

### 4.`DDMS`:安卓调试工具

### 5.DX工具：将class文件转换成.dex文件。

### 6.`AAPT`：android资源打包工具

### 7.`adb`：android调试桥，命令行必备。

### 8.`R.java`:有aapt工具根据APP中的资源文件自动生成，可以理解为

### 9.`androidManifest.xml`：APP的包名、组件生命、程序兼容的最低版本+所需的权限的配置文件。
