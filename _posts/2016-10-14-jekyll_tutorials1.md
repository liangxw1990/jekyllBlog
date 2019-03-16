---
layout: post
title: Jekyll搭建个人博客
date: 2016-10-14 
tags: 博客   
---


 
下载并安装：[Ruby WITH DEVKIT](https://rubyinstaller.org/downloads/)

安装完成后检查是否安装成功：

```bash
ruby -v
gem -v
```



### 介绍

　　[Jekyll中文文档](http://jekyll.bootcss.com/)、[Jekyll主题列表](http://jekyllthemes.org/)


### Jekyll 环境配置

```     
$ gem install jekyll 
$ gem install bundler
$ bundle install 
```    
<!-- more -->
创建博客

```bash
# 创建博客
$ jekyll new myBlog    
$ cd myBlog  

# 启动本地服务
$ bundle exec jekyll serve --watch
```

在浏览器里输入： [http://localhost:4000](http://localhost:4000)，就可以看到你的博客效果了。




可能遇到的问题：
1. [jekyll server出现...(Bundler::GemNotFound)问题解决方法](https://www.jianshu.com/p/c70dc6d3af14)
2. [jekyll serve启动报错,error:permission denied -bind(2)](https://segmentfault.com/q/1010000010483290)
3. [jekyll 3.8.5 | error jekyll-paginate](https://blog.csdn.net/qq_26508409/article/details/77927593)

### 博客部署到远端 

创建一个 github 账号，然后创建一个跟你账户名一样的仓库，如我的 github 账户名叫 [leopardpan](https://github.com/leopardpan)，我的 github 仓库名就叫 [leopardpan.github.io](https://github.com/leopardpan/leopardpan.github.io)，创建好了之后，把刚才建立的 myBlog 项目 push 到 username.github.io仓库里去（username指的是你的github用户名），检查你远端仓库已经跟你本地 myBlog 同步了，然后你在浏览器里输入 username.github.io ，就可以访问你的博客了。


### 编写文章

　　所有的文章都是 _posts 目录下面，文章格式为 mardown 格式，文章文件名可以是 .mardown 或者 .md。

　　编写一篇新文章很简单，你可以直接从 _posts/ 目录下复制一份出来 `2016-10-16-welcome-to-jekyll副本.markdown` ，修改名字为 2016-10-16-article1.markdown ，注意：文章名的格式前面必须为 2016-10-16- ，日期可以修改，但必须为 年-月-日- 格式，后面的 article1 是整个文章的连接 URL，如果文章名为中文，那么文章的连接URL就会变成这样的：http://baixin.io/2015/08/%E6%90%AD%E5/ ， 所以建议文章名最好是英文的或者阿拉伯数字。 双击 2016-10-16-article1.markdown 打开

```

---
layout: post
title:  "Welcome to Jekyll!"
date:   2016-10-16 11:29:08 +0800
categories: jekyll update
---

正文...

```


title: 显示的文章名， 如：title: 我的第一篇文章                    
date:  显示的文章发布日期，如：date: 2016-10-16                          
categories: tag标签的分类，如：categories: 随笔            

注意：文章头部格式必须为上面的，.... 就是文章的正文内容。

我写文章使用的是 Sublime Text2 编辑器，如果你对 markdown 语法不熟悉的话，可以看看[作业部落的教程](https://www.zybuluo.com/) 