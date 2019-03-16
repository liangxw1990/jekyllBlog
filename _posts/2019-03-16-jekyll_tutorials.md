---
layout: post
title: Jekyll搭建博客
date: 2019-03-16
categories: blog
tags: 博客
---

## 参考网站

[Jekyll中文文档](http://jekyll.bootcss.com/)  
[Jekyll主题列表](http://jekyllthemes.org/)

## 安装

下载并安装：[Ruby WITH DEVKIT](https://rubyinstaller.org/downloads/)

安装完成后检查是否安装成功：

```sh
ruby -v
gem -v
```

<!-- more -->

## 环境配置

```sh
$ gem install jekyll 
$ gem install bundler
$ bundle install 
```    

## 创建博客

```bash
# 创建博客
$ jekyll new myBlog    
$ cd myBlog  

# 启动本地服务
$ bundle exec jekyll serve --watch
```

在浏览器里输入： [http://localhost:4000](http://localhost:4000)，就可以看到你的博客效果了。


**安装配置过程中可能遇到的问题：**
1. [jekyll server出现...(Bundler::GemNotFound)问题解决方法](https://www.jianshu.com/p/c70dc6d3af14)
2. [jekyll serve启动报错,error:permission denied -bind(2)](https://segmentfault.com/q/1010000010483290)
3. [jekyll 3.8.5 error jekyll-paginate](https://blog.csdn.net/qq_26508409/article/details/77927593)


## 博客部署到远端 

创建一个 github 账号，然后创建一个与账户名一样的仓库。  
例如我的 github 账户名叫 [liangxw1990](https://github.com/liangxw1990)，那么 github 仓库名就叫 [liangxw1990.github.io](https://github.com/liangxw1990/liangxw1990.github.io)。  
创建好仓库之后，把刚才建立的 myBlog 项目 push 到仓库，在浏览器里输入 liangxw1990.github.io ，就可以访问博客了。

> 本站所使用主题的更多功能请参考：[从WordPress到静态网站](https://lszero.github.io/coding4fun/static-website-with-jekyll.html)