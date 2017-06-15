---
title: hexo + github = blogs
tags: 
 - hexo
 - github
categories: Study
---
hexo是一款基于Node.js的静态博客框架

### 前期猥琐发育

 1、安装node.js
 2、安装git
 3、添加github账号
 4、安装hexo

### 中期hexo的配置，选择主题（房子盖好了，就是各种装修哈！）
-------------------
 1、关联hexo与github
 2、发布你的第一篇博文
 3、选择主题（开始装修啦！）
 4、使用自己的域名
 
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
发现source/_posts/目录下多了helloworld.md 文件，我们用markdown编辑器打开此文件并编辑（不过你需要熟悉简单的markdown语法，这里推荐一款方便快捷的编辑器https://www.zybuluo.com/mdedito） ，不过现在我们可以在上面随便敲几个字：hello world就可以了。这样我们的第一篇博客就写完了。刷新页面http://localhost:4000/ 页面你会发现刚才的文章出现在了页面上（是不是很嗨森！）

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
这样我们本地的hexo就部署到了github上，可以去github仓库上查看相关的代码。访问 https://wadewow.github.io  就能线上访问我们的博客啦！

### 主题安装

所谓主题安装就是选择我们想要的装修风格，其实我们刚搭建好的时候就已经有默认的主题了，在/hexo/themes下的landscape就是我们默认的主题类型。但是不是很好看，我们可以到[Themes - Hexo ](https://hexo.io/themes/)下载喜欢的主题。我们现在已NexT主题为例。进入到hexo目录下面下载主题：
```
git clone https://github.com/iissnan/hexo-theme-next themes/next
```
将***站点配置文件_config.yml***修改为：
```
theme: next
```

修改成后，再次打开本地的调试http://localhost:4000/  查看时候安装成功！

安装成功后，页面可能还是功能还有些单调，如果想添加更多功能请参考[NexT使用文档](http://theme-next.iissnan.com/)

### 使用自己的域名
1.购买域名
我的域名是在马云爸爸的[万网](https://wanwang.aliyun.com/)那花了我“50大洋/年”买的。

2.设置 CNAME
在hexo目录下的 source 文件夹下，创建一个名称为 CNAME 的文件，内容为你的域名，比如我的是:
```
www.wadeqt.com
```
*注意*： CNAME 文件是不带后缀的。另外带 www 和不带 www，虽然用户在访问的时候网页内容是一样的，但是搜索引擎却认为是两个网页，最好自己选择一个首选域。

3.域名解析
就是将你购买的域名www.wadeqt.com与你的网址https://wadewow.github.io  产生一一对应的关系（域名映射）。

- 登录万网-->控制台-->云解析DNS，选择你的域名。
- 按照下图的方式填写：
![something wrong](http://od4phhdfp.bkt.clouddn.com/Domain.png)

*注意：*阿里云需要你实名制认证，大概等个工作日（反正我是登了三四天了）你就能通过你购买的新域名访问你的博客啦！
*啦啦啦！希望这篇博文能够帮助到一些你，有任何疑问和不对的地方望多多指正！*
