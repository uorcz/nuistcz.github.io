---
layout:     post
title:      在MacOS中安装使用Python3
subtitle:   与系统自带的Python2.7完美兼容
date:       2018-06-28
author:     Masa
header-img: img/post-bg-debug.png
catalog: true
tags:
    - Tips
---

## 前言

总所周知，Mac的OS X内置了python2，我的版本是2.7.10。但是python2将于2020年停止更新，所以安装python3的环境就很重要。
此外，在人工智能ML/DL方面，越来越多的开源框架偏向于支持python3进行开发，例如Tensorflow、PyTorch等。


## 安装Python3最新版

安装的过程十分简单，也有很多选择，我使用了homebrew的包管理环境。打开Mac中的Terminal，输入如下命令：
>brew install python3

可以看到Python3已经被正确的下载并安装。

## 与Python2进行兼容

在上一步结束的时候，我们发现直接在Terminal里输入Python，出来的版本仍然是Python2.7的旧版本，这时候就需要修改```PYTHONPATH```定义了，简单的方法是直接在命令行里输入：
> unset PYTHONPATH

但是在我的Mac中并不起作用，再查阅了大量资料之后，我发现```PYTHONPATH```会读取```~/.bash_profile```文件来进行初始化，这时候就需要直接修改此文件 的配置。利用Vim工具，输入：
> vim ~/.bash-profile

在顶端加入一行
```export PYTHONPATH=$PYTHONPATH:/usr/local/lib/python3.6/site-packages```
按住shift+Z两次即可退出
## 结语

至此便大功告成了，在命令行里使用pip3命令安装python3的package，直接输入Python3 -V 提示版本Python3.6.5，即为最新版。

### 参考

- [Python官网](https://www.python.org/downloads/mac-osx/)

