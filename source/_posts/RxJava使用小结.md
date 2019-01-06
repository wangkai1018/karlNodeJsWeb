---
title: RxJava使用小结
tags:
- ReactiveX
- RxJava
date: 2016-05-14 10:55:03
---
### 概要
近来一些日子，`Reactivex`看到的机会越来越多，如雷贯耳，于是乎决定亲自撸一遍，记录一下自己遇到的坑

###为什么要用Reactivex？
* 异步：它是一个实现`异步`操作的库
* 简洁：它可以随着应用程序的越来越复杂的同时，依然保持简洁

> a library for composing asynchronous and event-based programs using observable sequences for the Java VM

这是在[RxJava](https://github.com/ReactiveX/RxJava)在github主页上的介绍

### 概念：
`RxJava`的异步实现，是通过扩展的观察者模式实现的。android中比较典型的例子：点击监听器`OnClickListener`。`View`是被观察者，`OnClickListener`是观察者，两者通过`setOnClickListener`产生关系，`Android Framework`层会将点击事件发送给注册过的OnClickListener。

RxJava的四大基本概念

* Observable：被观察者，可观察者
* Observer: 观察者
* Subscribe：订阅
* Event：事件

