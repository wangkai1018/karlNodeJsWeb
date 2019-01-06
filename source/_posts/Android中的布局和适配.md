---
title: Android中的布局和适配
date: 2015-10-16 21:17:02
tags: 
- android 
---

## 概述
介绍几种android中常用的布局和适配尝试


### 线性布局`LinearLayout`:
在显示分割线时，使用 `divider`属性：

1. 设置一张分割线图片

2. showDivider分割线的位置： 


			* none 无
			* begining 开始
			* end 结束
			* middle 两个组件之间
  
##### 线性布局的优点：
它的weight属性，在适配时帮助还是很大的。
##### 线性布局的缺点：
当页面比较复杂的时候，会嵌套很多的线性布局，这样会降低`UI Render`的效率（渲染速度），二期如果是listview和gridview，效率会更低。另外太多层的线性布局嵌套会占用跟多的系统资源，还可能引发`stackoverflow`

### 相对布局`RelativeLayout`:
基本属性：

* gravity:设置容器内组件的对其方式
* ignoreGravity:设置了该属性为`true`时的组件，将不受`gravity`的属性影响


### 帧布局`framelayout`:
常用属性：

* `foreground`:设置更改真布局的前景图像
* `foregroundGravity`:是指前景图像显示的位置

  
### 网格布局`GridLayout`:
该布局是android4.0之后推出的，所以最小API等级为14。`GridLayout`需要使用`v7`jar包，才可以使用。
可以解决线性布局和相对布局的复杂嵌套问题
### 关于适配：

* `dp`（dip）：设备独立像素，不同的设备有不同的显示效果。
* `px`：不同设备，显示效果相同，一般HVGA320*480,用的比较多。一般我们为了支持WVGA和HVGA和QVGA，推荐使用这个，不依赖像素。
* `pt`：是一个标准的长度单位，1pt=1/72英寸，用于印刷业，简单易用
* `sp`：主要用于字体显示



			  
尽量搭配使用RelativeLayout+LinearLayout的weight属性

ps:google官方并不提倡使用weight权重，因为这样会在加载布局时造成大量的计算，影响性能。

### [Android Percent Support Lib](http://http://blog.csdn.net/u014784379/article/details/46754189)

还有就是谷歌官方推出了类似于CSS的百分比来布局的库（`Android Percent Support Lib`）：

如何使用

首先需要满足如下要求：

Android SDK v22
Android Build Tools v22.0.1
Android Percent Support Repository v22.2.0
Android Support v4 Repository v22.2.0
  
  
然后在`build.gradle`中添加：

			dependencies {
			    compile 'com.android.support:percent:22.2.0'
			}
  

以后补充个，使用百分比适配库的



### 屏幕适配：
2014年初，6个主流的分辨率：

* 480x680
* 720x1280
* 320x480
* 480x854
* 540x960
* 1080x1920


屏幕尺寸：1英寸=2.54厘米

屏幕分辨率：分辨率是指在横纵向上的像素点数，单位是`px`，1px=1个像素点

`px`：获取屏幕宽高，写布局时尽量用dp而不是px

PS:160为基础，1dip=1px，如果是320dip则1dip=2px

对于5种主流的像素密度：
* MDPI
* HDPI
* XHDPI
* XXHDPI
* XXXHDPI

按照2:3:4:6:8的比例进行缩放
其中LDPI是低像素

### 解决方案：
1. 使用wrap_content,math_parent,weight
2. 使用布局别名：即在手机上显示单面板，在平板上显示双面板
3. 使用自动拉伸图.9png图，现在谷歌官方支持使用`SVG`图片
4. 使用dp和sp
5. 提供备用位图
6. 动态设置，获取屏幕参数
7. 当分辨率不同时，不能使用px
8. 因为屏幕宽度不一样，所以要小心使用dp


### 关于高清设计图尺寸
1. 以mdpi为设计，然后放大图片到各个分辨率
2. 以高分辨率为基础，对低分辨率进行缩放，可以以1280x720，1960x1080为主要分辨进行设计
3. ImagView 的ScaleType，设置不同的ScaleType会得到不同的显示效果，一般情况下，设置centerCrop能获得更好的适配效果
