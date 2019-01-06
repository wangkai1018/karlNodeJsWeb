---
title: android ADB 常用命令
date: 2015-09-06 15:27:01
tags:
- ADB
- android
---

## 语句

* adb install [-r] [-s]  xxxx.apk 安装软件
* app：adb unstall [-k] <包名> -k 卸载app
* adb pull xxxx.xxxx 取出手机中的文件
* adb push xxx.xxx 发送文件到手机当中
* adb shell  进入手机终端
* adb devices     杀死adb
* adb start-server   启动adb
* reset adb 重启
  
 
 FAQ
 
 * App的包名是App的唯一标识！！！
 * 安装软件中的  -r  重新安装
 * -s   安装到SDK

