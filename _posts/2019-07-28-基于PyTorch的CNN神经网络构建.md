---
layout:     post
title:      基于PyTorch的CNN神经网络构建
subtitle:   使用个人数据集构建的ResNet-18神经网络模型
date:       2019-07-28
author:     Masa
header-img: img/post-bg-debug.png
catalog: true
tags:
    - Python
    - DL
---

## 前言

Hello，这时我在ZJU实习期间上手的第一个项目，构建一个简单的神经网络用于识别食物/非食物图片。我将在这篇博文中简单总结我的学习路线和项目的实现方式。


## PyTorch

虽然Tensorflow的势头很猛，但是我的Lab一般使用PyTorch框架。基于PyTorch的深度学习框架和Tensorflow大同小异，底层的算法甚至常用数据集都已经封装好了，日常使用主要是各种调库和调参操作。


### 常用的文件操作
```python

```

## Advanced Usage

### python实现对文件夹内所有特定格式文件的提取

字典可以用一个被大括号包围的以逗号分隔的键值对(key:value)列表来创建，例 
如：[Math Processing Error]，或者用字典构造器来构造。
```python

```
os模块，即系统模块。主要用于处理文件和目录，其最大的特点是可以跨平台。
os.walk()方法就是在目录中游走输出，语法格式为:
>os.wlak(top[,topdown = True[,onerror = None[,followlinks = False]]])
总共有四个参数：
1. top，产生三元组：文件夹路径，文件夹名字，文件名。
2. topdown，True则自上而下，False则自下而上。
3. onerror，是一个函数，调用一个参数，出现错误时继续wlak或者抛出异常停止walk。
4. followlinks，true时可以通过软链接访问目录。

### 数据集切割
使用1:6的比例切分Train/Test
```python
import os
import shutil
path = '/Users/sousei/PycharmProjects/Project/dataset/test/b_split'
np = '/Users/sousei/PycharmProjects/Project/dataset/test/a_split'
count = 0
rand = 0
for root,dirs,files in os.walk(path,True):
    print('root:%s'%root)
    # print('dirs:%s'%dirs)
    # print('files:%s'%files)
    print(len(files))
    
    for i in range(len(files)):
        rand += 1
        if(files[i][-3:] == 'jpg'):
            file_path = root + '/' + files[i]
            new_file_path = np + '/' + str(count) + '.jpg'
            # new_file_path = np + '/' + files[i]
            if(rand%7 == 0):
                shutil.move(file_path,new_file_path)
                print ("Move!")
                count += 1
```


### 参考

- [CSDN/熊猫大哥大](https://blog.csdn.net/woshisangsang/article/details/74360612)
- [CNBlogs/三寸碧玉心](https://www.cnblogs.com/gotoMars/p/8668741.html)

