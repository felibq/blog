---
title: Bootstrap扁平化样式
date: 2016-10-27 17:43:00
tags: blog
categories: 教程
describle: 
---


#### 1. 引入`bootstrap.css`或者`bootstrap.min.css`。
#### 2. 新建一个css文件，如`main.css`,内容如下
<!-- more -->
```
.well, 
.navbar-inner, 
.popover, 
.btn, 
.tooltip, input, select, textarea, pre, 
.progress, 
.modal, 
.add-on,
.alert, 
.table-bordered, 
.nav>li>a, 
.dropdown-menu, 
.tooltip-inner, 
.badge, 
.label, 
.img-polaroid, 
.thumbnail, 
.dropdown-toggle {
  -moz-box-shadow: none!important;
  -webkit-box-shadow: none!important;
  box-shadow: none!important;
  -webkit-border-radius: 0px!important;
  -moz-border-radius: 0px!important;
  border-radius: 0px!important;
  border-collapse: collapse!important;
  background-image: none!important;
}
 
.btn{
  border: none;
}
```
#### 3. 在`bootstrap.css`后面引入，就可以看到直角扁平化的代码了。
