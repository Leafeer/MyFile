---
title: hexo本地和线上不一致的解决办法
date: 2021-03-17 01:11:47
tags: hexo
categories:
  - 博客搭建
---

# Github Page 配置


  首先先检查一下本地库和线上库是否一致。我这里采用的联调方式是通过GitHub的分支来控制的。
导致存在GitHub的上存在多个分支的情况。
由于hexo使用的是GitHub.page服务,需要在设置界面设置一个主要的master节点，需要确保这个节点和hexo渲染的节点保持一致。

<!-- more -->

{% asset_img hexo本地和线上不一致的解决办法01.png hexo本地和线上不一致的解决办法 %}

# 缓存清理
  

同时还可以删掉跟路径的.deploy_git文件夹，该文件夹为hexo g命令生成的文件夹,可以删掉后，使用hexo clean命令。再生成hexo文件，由此来删除缓存，也能减少该情况。

