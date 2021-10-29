---
title: Hexo利用Github搭建博客
date: 2021-03-25 02:20:47
tags: 
    - hexo
categories:
  - 博客搭建
---

# 这篇开头
主要是针对想要自己搭建博客的小伙伴们来书写的一个简易的搭建博客的教程。该项目的原理是使用了Hexo博客框架+Next主题框架+Github Page来构建。
本篇幅主要针对window系统来考虑，敬请谅解。

<!-- more -->
# 搭建环境
1. 安装Node.js [点击此处](https://nodejs.org/en/)安装node.js，建议下载14.x的版本，相对来说比较稳定。安装完成之后，win+r输入cmd在命令行中输入node -v 来查看版本检验是否安装成功。如果显示未找到，请重启电脑后再次操作。

{% asset_img Hexo利用Github搭建博客01.png Hexo利用Github搭建博客 %}

2. 安装Git [点击此处](https://github.com/waylau/git-for-win)安装Git,Git教程有机会再补。
该项目主要是利用Git Page的功能，不会涉及到太多的Git 的相关操作，可暂时不看Git相关教程也能完成搭建。

3. 打开终端，通过npm安装[Hexo](https://hexo.io/zh-cn/docs/setup.html)
```
$ npm install -g hexo-cli
```

都成功安装之后，所需要的环境都已经安装完毕，如有报错问题可以评论或者联系我。

# Github配置
1. 注册、登录 https://github.com/ ，要注意自己的 <kbd><font color='DarkTurquoise'>Username</font></kbd> 在之后的创建项目以及GitHub.io专属的域名中是一个比较重要的关键字。
2. 右上角选择 <kbd><font color='DarkTurquoise'>New repository</font></kbd>

{% asset_img Hexo利用Github搭建博客02.png Hexo利用Github搭建博客 %}

其中仓库名称 <kbd><font color='DarkTurquoise'>Repository name</font></kbd> 一项填写格式为：youremail.github.io【youremail一定要与你的注册用户名一致,这个就是你博客的域名了】
3. 生成密匙 在终端输入
```
ssh-keygen -t rsa -C "Github的注册邮箱地址"
```
看不懂的话一直回车也可以，按照生成的目录去找到两个文件 <kbd><font color='DarkTurquoise'>id_rsa</font></kbd> 和 <kbd><font color='DarkTurquoise'>id_rsa.pub</font></kbd> ，用记事本打开 <kbd><font color='DarkTurquoise'>id_rsa.pub</font></kbd> 复制里面的所有内容。 进入 https://github.com/settings/ssh 中，点击 <kbd><font color='DarkTurquoise'>New SSH key</font></kbd>创建新的SSH key。
title可以随意写，复制密匙到Key的输入框内添加则完成。

# 初始化博客
在想要建的目录下，在文件夹的目录路径上输入 <kbd><font color='DarkTurquoise'>CMD</font></kbd> 可以呼出对应路径的终端。

{% asset_img Hexo利用Github搭建博客03.png Hexo利用Github搭建博客 %}

输入以下内容初始化博客

```
hexo init blog
```

初始化之后会在source目录下自带一篇标题为hello world 的文章，所以可以直接执行以下命令

```
hexo g // 生成对应的博客文件
hexo s // 启动博客本地服务器预览
WARN  ========================= ATTENTION! ==========================
WARN  ===============================================================
WARN   NexT repository is moving here: https://github.com/theme-next
WARN  ===============================================================
WARN   It's rebase to v6.0.0 and future maintenance will resume there
WARN  ===============================================================
INFO  Start processing
INFO  Hexo is running at http://localhost:4000 . Press Ctrl+C to stop.
```

到这里就已经完成了搭建博客的一半了，接下来是配置博客的路径

# 配置博客

打开根目录下的 <kbd><font color='DarkTurquoise'>_config.yml</font></kbd> 文件，该文件是配置文件，可以在里头修改参数信息。
## 配置相关信息

```
title: 抹茶薄荷糖的小屋                   // 网页标题
subtitle: '希望世界和平，天天下雨'         // 个签
description: '蠢? 说我吗?'                // 描述
keywords:                                // 键入
author: 抹茶薄荷糖                        // 作者
language: zh-Hans                         // 语言
timezone: 'Asia/Shanghai'                 // 时间
```

## 配置部署

将以下配置的yourname替换成自己的用户名即可。

```
deploy:
  type: git
  repository: git@github.com:yourname/youremail.github.io.git
  branch: master
```

> 注意 branch所选择的分支一定一定要以github page 配置的分支一样才行。


