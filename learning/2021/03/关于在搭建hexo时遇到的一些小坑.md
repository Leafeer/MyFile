---
title: 关于在搭建hexo时遇到的一些小坑
date: 2021-03-20 13:16:25
tags: 
    - hexo
categories:
  - 博客搭建
---

# 如何在social下面添加能够跳转到QQ的聊天框

复制下方链接，将要指向的QQ修改为自己的QQ号。
``` 
http://wpa.qq.com/msgrd?v=3&uin=610840268&site=qq&menu=yes 
```
后面跟随的图标可以在[点击连接](https://fontawesome.com/icons?from=io)处寻找
qq的图标为两个小写的‘qq’

<!-- more -->
---

# 如何引用多行代码块
需要使用  \`  符号，键盘左上角，tab上面的符号。按三次，并且是独立的三个  \`  符号为一行

# 从Github 迁移 到 Gitee 遇到的各种bug
## 配置问题
Gitee并不支持热加载,也就是说,每次推送上去之后,仍然需要手动在Page页面更新一次.

## _config.yml
_config.yml文件中,permalink:关键字后缀不能改动,否则文章内部会出现无法获取到样式路径的情况.