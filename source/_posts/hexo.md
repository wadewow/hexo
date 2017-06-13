---
title: hexo + github = blogs
tags: 
 - hexo
 - github
categories: Study
---
在老弟[Ceil Ni](http://www.cielni.com/)的大力支持下，完成了博客的搭建。自己天资愚笨上手比较慢，大家将就着看哈！

### 前期猥琐发育

 1、安装node.js
 2、安装git
 3、添加github账号
 4、安装hexo

### 中期hexo的配置，选择主题（房子盖好了，就是各种装修哈！）

 1、关联hexo与github
 2、发布你的第一篇博文
 3、选择主题（开始装修啦！）
 4、总结

 -------------------
 
 <!-- more -->
 
### 安装node.js

[node的安装](http://www.runoob.com/nodejs/nodejs-install-setup.html)很简单的，查看node、npm版本号：
```
     node -v
     npm -v
```
### 安装git

[安装git](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00137396287703354d8c6c01c904c7d9ff056ae23da865a000)，查看git版本
```
    git --version
```
### 添加github账号 

[注册github并创建仓库](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001374385852170d9c7adf13c30429b9660d0eb689dd43a000)，注意这里创建的仓库一定要是这种格式的：wadewow.*github.io*（一定要以.github.io结尾）


### 安装hexo
创建一个文件夹（这里直接创建一个名为hexo的文件夹)，cmd进入到hexo文件夹中输入一下命令：
```
    npm install -g hexo-cli
    npm install hexo --save
```
安装好后，查看hexo版本号：
```
    hexo -v
```
### 初始化hexo
```
    hexo init
```
然后输入：
```
    npm install 
```
之后就可以通过npm 安装一些插件咯。

**接下来我没来试试是否hexo是否安装成功：**
```
    hexo s -debug  #启动本地的服务器，在浏览器中输入http://localhost:4000/,如果能正常打开说明你已经成功一大半了
```
其实呢，我们现在就可以写开始写我们的第一篇博客了，那我们从hello world开始吧，哈哈
博客呢，其实是写在.md后缀的文本里面然后部署上去。
首先我们先创建一个markdown的文件，进入到hexo文件夹中：
```
    hexo new helloworld
```
你看到：
```
    wadedeMac-mini:hexo wade$ hexo new helloworld
    INFO  Created: ~/Desktop/hexo/source/_posts/helloworld.md
```
发现source/_posts/目录下多了helloworld.md 文件，我们用markdown编辑器打开此文件并编辑（不过你需要熟悉简单的markdown语法，这里推荐一款方便快捷的编辑器https://www.zybuluo.com/mdedito），不过现在我们可以在上面随便敲几个字：hello world就可以了。这样我们的第一篇博客就写完了。刷新页面http://localhost:4000/页面你会发现刚才的文章出现在了页面上（是不是很嗨森！）

*好的，第一篇文章写完了，那么别人都看不到啊，看不到怎么装13，这时候就要关联之前注册的github账号了，她会帮我们生成网页链接*

### 关联github
先安装一个拓展：
```
    npm install hexo-deployer-git --save  #这里用到的npm就是我们之前  npm install 时安装的
```
打开hexo文件下面的_config.yml文件
```
    # Deployment（部署）
    ## Docs: https://hexo.io/docs/deployment.html
    deploy:
      type: git
      repo: git@github.com:wadewow/wadewow.github.io.git
      branch: master
```
repo的值替换成你你自己github上的仓库名
完成设置后，本地的hexo就和远程仓库关联起来了，但是我们还将我们的hexo部署到远程仓库上：
```
    hexo d -g
``` 

这样我们本地的hexo就部署到了github上，可以去github仓库上查看相关的代码。访问https://wadewow.github.io,就能线上访问我们的博客啦！

### 主题安装
