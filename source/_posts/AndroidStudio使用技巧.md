---
title: AndroidStudio使用技巧
date: 2015-06-13 10:42:55
tags:
- android 
- Android studio
---


![image](http://7xst5r.com2.z0.glb.clouddn.com/androidstudio.png)

MAC系统专用

### 快捷键： 
1.方法重构：`command`+`option`+`M`

2.于重构相反：`command`+`option`+`I`

3.快速模糊搜索当前中任何文件：double `shift`

4.搜索工程内任意代码，可以模块（`modlue`）,根据正则匹配搜索：`control`+`H`

5.发现使用调用位置`find Usages`:`shift`+`command`+`G`

6.快速定位关联的文件`Declaration`：`control`+鼠标左键

7.代码提示快捷键`Class Name Completion`

***

### 模板：

#### 文件模板`File Template`:

* 保存文件模板 ：

  `tools`->`Save file as template`
  
  会默认把当前编辑的文件，保存成模板
  
* 查看模板：
 
  鼠标右键菜单中可以查看
  
  
#### 活动模板`live Template`:


* 保存自定义活动模板：选中代码后， `tools`->`Save  as live template`，然后键入此活动模板的名字
* 活动模板的使用：可以使用as已经编辑好的模板，直接使用,输入模板关键字，直接生成代码:

`fbc`
     
      () findViewById(R.id.);
     
`rouiT`
      
      getActivity().runOnUiThread(new Runnable() {
            @Override
            public void run() {
                
            }
        });
        
 `Sfmt`
       
      String.format("", );
      
      
  `Toast`
      
        Toast.makeText(MainActivity.this, "",Toast.LENGTH_SHORT).show();
        
        
  `visible`
        
        .setVisibility(View.VISIBLE);
               
   `gone`
        
        .setVisibility(View.GONE);
          
   `rgS`
        
        .getString(R.string.)
         
***
***        
     
### 导入github第三方类库，常见错误解决方法：
[去查看](http://www.androidchina.net/4322.html)
