---
layout: post
title:  "快速搭建独立博客--Github Pages+Jekyll"
date:   2016-01-24 21：13
tags: featured
image: /assets/images/page_image_4.jpg
---
## 目录

####1. 准备工作
 
1.1安装环境

1.2博客域名
 
1.3配置Github

####2. 选择一个jekyll博客模板

####3. 自己的github pages

####4. 绑定独立域名

####5. 本地修改博客

####6. 上传自己的文章

##1. 准备工作
 
 ***1.1安装环境***
 
 * [安装Node.js](https://nodejs.org/en/)
 * [安装Git](http://git-scm.com/)
 * [安装jekyll](http://jekyll.bootcss.com/)
 * [安装Github desktop](https://desktop.github.com/)
 * 安装Markdown编辑器（我使用的是MacDown）
 
***1.2博客域名***

博客域名可以去万网、西部数码、DNSPod等网站购买，像.red .me .top .club这类新顶级域名，价格较低，适合作为个人博客域名。

如果暂时没有购买，也可以在接下来使用github pages提供的https://github.com/用户名/blog.io域名
 
***1.3配置Github***

* 登录[Github 官网](https://github.com/)在官网首页就可以完成一个帐号的注册
* Mac下打开Terminal（Windows下打开Git Bash）。
* 配置SSH keys：

 `cd ~/.ssh 检查ssh密钥`
 
 `$ ssh-keygen -t rsa -C "你的邮件地址@email.com"//用来在提交项目时对人员的区分
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/your_user_directory/.ssh/id_rsa)://回车默认保存在.ssh/目录下`

 `Enter passphrase (empty for no passphrase):<输入密码>
 `
 
 `Enter same passphrase again:<再次输入密码>
`

随后将生成ssh key

* 将ssh key添加到github：打开.ssh/下的id_rsa.pub文件（Mac 下可以在Teminal中进入.ssh/后，more id_rsa.pub），![ssh key](http://xyb.space/assets/article_images/ssh key.png)将里面的k内容复制出来，在github settings页面里，加入到SSH keys中。

* 测试下是否连通

`ssh -T git@github.com`

* 设置本机用户信息 

`$ git config --global user.name "xxx"//用户名`

`$ git config --global user.email  "xxx"//填写自己的邮箱`

至此Github配置完毕

##2. 选择一个jekyll博客模板
接下来我们来选择一个自己喜欢的博客模板，这里我使用[Jekyll Themes](http://jekyllthemes.org/)。

进入Jekyll Themes页面![模板图片](http://xyb.space/assets/article_images/模板图片.png)里面罗列了许多网友制作的模板，点开选择一个自己喜欢的模板![模板页面](http://xyb.space/assets/article_images/模板页面.png)可以点击demo，来查看博客模板样例展示。在选定模板后，点击Home Page进入该模板所在Github项目页面，点击右上角Fork![Fork](http://xyb.space/assets/article_images/Fork.png)即可将该博客的副本变成自己的博客模板。

##3. 自己的github pages
此时，我们已经有了博客模板。
点击Settings，将该项目名字改为"你的github用户名.github.io"。

现在 你的 github 用户名.github.io 就可以访问了。

##4. 绑定独立域名
回到guthub上的博客项目页面，点击New file创建一个文件，文件名字为CNAME，内容为域名地址。![CNAME](http://xyb.space/assets/article_images/CNAME.png)
接下来的操作基于DNSpod，你也可以使用域名购买商自己的域名解析服务，或者将域名DNS1和DNS2修改为dnspod的DNS来将对域名的解析操作转移到DNSPod![DNS](http://xyb.space/assets/article_images/DNS.png)。
进入域名解析页面->添加域名->添加记录
添加如下记录![A记录](http://xyb.space/assets/article_images/A记录.png)![CNAME记录](http://xyb.space/assets/article_images/CNAME记录.png)
其中192.30.252.153和192.30.252.154是github的ip

CNAME类型的记录是你github pages地址

##5. 本地修改博客
再次回到guthub上的博客项目页面，点击![save to desktop](http://xyb.space/assets/article_images/save to desktop.png)将项目Pull到本地，打开所在目录就可以看到整改博客网站的所有文件了。

你可以通过更改_config.yml来更改网站配置，也可以更改css文件夹中的css来改变样式，或者更改_include、_layouts、icon等文件来制作自己的博客页面。

使用jekyll的一大方便就是可以再本地服务器先进行调试，按照[jekyll官网](http://jekyll.bootcss.com/)快速搭建配置好blog本地地址后，打开Teminal`cd blog本地地址`

输入`jekyll server`，启动后在浏览器中输入http://localhost:4000就可以查看本地博客网页了。

修改完成后，打开github desktop,里面会显示发生的变化![Github desktop](http://xyb.space/assets/article_images/Github desktop.png)你可以点击Commit to master来在本地提交修改，然后点击右上角Sync来提交到github远程端，同时你的博客网站页面也会发生变化。

##6. 上传自己的文章
使用markdown编辑器编写自己的博客文章，并按"YEAR-MONTH-DAY-title"来命名，保存在_posts文件夹下，这时同步后，网站中将自动显示这篇文章。

##7.大功告成
现在整个独立博客就建立完成，之后只需要写好文章放到_posts下，同步一下，你的网站就会同步更新了。

>版权声明：本文为博主原创文章，未经博主允许不得转载。
