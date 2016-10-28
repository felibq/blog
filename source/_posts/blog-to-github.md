---
title: 博客部署遇到的问题
date: 2016-09-09 16:54:50
tags: blog 
categories: 教程
describle: 
---
<img src="../../../../../images/github.jpg" class="full-image" />

<!-- more -->
### 问题背景
部署好本地的hexo 博客后，一开始用的推送到github上的方法是先执行

    hexo d
    
这样会生成一个public文件夹。然后把这个public文件夹想办法推送到github相关的仓库上，后来发现这个方法有些繁琐。故一直在想用hexo自带的推送方法来做。
### 方案
其中部署的配置，需要在配置文件_config.yml中配置：

    deploy:
    type: git
    repository: git@github.com:xxxx/xxxx.github.io.git
    branch: master
    
### 小插曲
中间遇到点小问题，因为没有认真看官方文档，所以不知道原来部署是需要安装相应的插件的。直到有一天看到了官方文档。才明白需要安装相应依赖：

    $ npm install hexo-deployer-git --save
    
### 一波三折
这样的话，本以为可以了，可想不到的，又遇到一个问题，是关于本地推送到github上的认证问题。

验证报错报错
**verification failed：**
**Error: Host key verification failed.**
**fatal: Could not read from remote repository.**
**Please make sure you have the correct access rights and the repository exists.**


经过一番搜索，找到以下解决方案：

###解决方法
条件SSHkey

    $ ssh-keygen -t rsa -C "imsofter@163.com"
    
三次回车，即可设置密码为空

将生成的C:\Users\Administrator.ssh目录下的id_rsa.pub添加到github上


再测试是否可以连接到github上，

    $ ssh git@github.com

**Hi imsofter! You've successfully authenticated, but GitHub does not provide shell access.**
**Connection to github.com closed.**

再可以将代码推上github上了。

----------


>官方文档的地址为：https://hexo.io/zh-cn/docs/deployment.html。

>参考网址：http://www.cnblogs.com/imsoft/p/5228560.html。
