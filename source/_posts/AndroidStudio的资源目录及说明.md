---
title: AndroidStudio的资源目录及说明
date: 2015-06-08 21:49:50
tags:
- android 
- Android studio
---

AndroidStudio以下简称AS,因为as和eclipse目录有些区别，所以记录一下

### as中没有`assets`目录，要用的话可以手动创建


##图片资源：
#### 在`eclipse`中是`drawable`打头的。在AS中是`mipmap`开头的。mipmap会在图片缩放时提供一些性能支持


### `drawable`:存放各种位图文件png，jpg，9png，gif，和drawable类型的xml文件

### `mipmap-hdpi`:高分辨率，一般我们把图片放在这里

### `mipmap-mdpi`:中等分辨率，很少，除非兼容的手机很老。

### `mipmap-xhdpi`:超高分辨率，手机屏幕材质越来越好，以后估计会慢慢往这里过渡

### `mipmap-xxhdpi`:超超高分辨率，这个在高端机上有所体现

### `布局资源：layout`: 存储布局文件，在特定的机型上：例如：`layout-480x320`的文件夹

### 菜单资源：
### `menu`：在以前有物理菜单按钮，即menu菜单的手机，用的较多，现在用的并不多，菜单相关的资源xml文件在这里存储。

## values目录：
* `demens`:定义尺寸资源
* `string`：定义字符串资源
* `style`：定义样式资源
* `colors`：定义颜色资源
* `attrs`：自定义控件时用的较多，自定义控件属性。
* `theme`:主题文件，和style相似，但是会对应用中的activity和制定activity起作用，一般是改变窗口外观的。可在java代码中通过setTheme使用，或者在AndroidManifest中的application比傲天添加theme属性。PS:你可以看到这样的目录，values-w820dp,values-v11,前者代表平板设备，820dp代表屏幕宽度，而v11代表AIP11，即3.0之后才能使用。

* `raw`:用于存放各种原生资源(音频,视频,xml文件)
我们可以通过OpenRawResource(Int id) 来获得二进制流，其实和Assets差不多，不过raw可以在R文件中生成一个唯一的资源标识符id而已

* `animator`:存放属性动画的xml文件
* `anim`：存放补间动画的xml文件
