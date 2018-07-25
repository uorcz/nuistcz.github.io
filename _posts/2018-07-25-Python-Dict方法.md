---
layout:     post
title:      Python Dict 方法集合
subtitle:   字典(Dict)数据结构
date:       2018-07-25
author:     Masa
header-img: img/post-bg-unix-linux.jpg
catalog: true
tags:
    - Python
    - 数据结构
---

## 前言

一个映射对象将可散列的值映射到任意对象。映射类型是可变的对象。当前只有一种标准的映射类型，即字典。用作键值的数字类型遵循正常的数值比较规则：如果两个数是相等的（例如1和1.0），那么它们可以交替使用来索引同一个字典条目。（但是注意，由于计算机将浮点数存储为近似值，所以将他们用作字典的键值是不明智的） 
字典的键值几乎可以是任意值。包含列表字典和其他可变类型（比较是通过值而不是对象本身的类型）不能作为键值。 


## Key

>关键词：Python 数据结构

### Intro

字典可以用一个被大括号包围的以逗号分隔的键值对(key:value)列表来创建，例 
如：[Math Processing Error]，或者用字典构造器来构造。
**字典构造器如下:**
```python
    class dict(**kwarg)
    class dict(mapping, **kwarg)
    class dict(iterable, **kwarg)
```

### 字典中支持的方法：
```
    len(d)
        返回字典中的条目数

    d[key]
        返回该键值key对应的条目，如果没有对应条目，则触发KeyError错误。
    如果一个字典的子类定义了__missing__()方法，并且该key不存在，那么d[key]操作通过键值key来调用该方法（__missing__()方法）。
    d[key]操作就会返回或者触发__missing__(key)中定义的任何值，如果定义的是返回值，则返回该值，如果定义的是错误，则触发该错误。
    没有其他操作或方法会调用__missing__()，也就是仅仅d[key]中key不存在时才会调用该方法。如果__missing__()没有定义，那么会触发
    KeyError错误；__missing__()必须定义成方法，不能是一个变量。
    例如如下代码所示:
    >>> class Counter(dict):
    ...     def __missing__(self, key):
    ...         return 0
    >>> c = Counter()
    >>> c['red']
    0
    >>> c['red'] += 1
    >>> c['red']
    1

    d[key] = value
        设置d[key]的值为value，如果该key不存在，则为新增

    del d[key]
        从字典d中移除key对应的键值对条目，如果该key不存在，则会触发KeyError错误。

    key in d
        如果字典d中有该key，则返回true,否则返回false

    key not in d:
        和key in d意思相反

    iter(d)
        返回包含字典d中所有键值的迭代器，是iter(d.keys())的缩写

    clear()
        清空字典中的所有条目

    copy() 
        返回该字典的浅拷贝

    classmethod fromkeys(seq[,value])
        用seq中的键值和设置的相应的value来创建一个新的字典
        fromkeys()是一个类的方法，返回一个新的字典，值为None

    get(key[,default])
        如果字典中存在该key,返回字典中key对应的值;如不存在，则返回方法中给定的default值。如果方法中没有给定default值，则默认为
        None，总之永远不会触发KeyError错误。

    items()
        返回字典的新视图（即返回（key,value）列表）

    keys()
        返回字典中键值的新视图（即键值列表）

    pop(key[,default])
        如果字典中有该key,则移除该key对应的条目，并返回该key对应的值；如果不存在该key，则返回default值。如果没有给定default值
        并且字典中不存在该key值，那么会触发一个KeyError错误。

    popitem()
        从字典中随机移除一个条目，并将该条目（key,value）返回。popitem()对字典的破坏性迭代特别有用，所以经常在集合中使用。
        如果字典中已经没有条目，那么该方法会触发一个KeyError错误。

    setdefault(key[,default])
        如果该key已经在字典中，那么返回key对应的值；如果不在字典中，则将该key插入到字典中，该key对应的值为该方法设定的default
        值，并返回default值，如果没有设定default值，则对应None值。

    update([other])
        用other中的键值对来更新字典，重写已经存在的key值，返回None。
```


### 参考

- [CSDN](https://blog.csdn.net/jeryjeryjery/article/details/72772145)

