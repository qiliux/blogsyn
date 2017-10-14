---
title: 机器学习入门与python简介
date: 2017-07-28 17:19:39
tags:
- 机器学习
- python
categories:
- 机器学习
---

机器学习基本分类
==========
* 监督学习
    * 分类问题
    * 回归问题
* 非监督学习
* 强化学习

　　监督学习与非监督学习的最大区别就在于目标值是否已知。
监督学习（Supervised Learning)
--------
　　已知{%math%}D=\{X_i,Y_i\}{%endmath%}  
　　学习{%math%}f():Y_i=f(X_i){%endmath%}  
　　常见：语音识别、搜索广告、商品推荐、机器翻译、个性化新闻，当$Y$为离散值时，为分类问题；当$Y$为连续值时，为回归问题。
非监督学习（Unsupervised Learning）
--------
　　已知{%math%}D=\{X_i\}{%endmath%}  
　　学习{%math%}f():Y_i=f(X_i){%endmath%}  
　　常见：聚类、降维、神经网络预训练
增强学习（Reinforcement Learning）
--------
　　智能系统从环境到行为映射的学习，以使奖励信号值最大。  
　　其他未知，以后补充。
　　
# Python
　　本文只做总结，详细内容请查看官方文档。

## 常用数据结构


### list（列表）
　　list的内容可修改的,mutable
　　对应符号：[]，也可用list()创建。   
　　列表推导式：
　　{% codeblock lang:python %}
        [x for x in iterable] 
        #单重列表生成
        [x for x in range(1,5)] # output: [1, 2, 3, 4]
        #多重列表生成,注意for循环的嵌套顺序。
        [[x for x in range(1,y)] for y in range(1,5)] # output: [[], [1], [1, 2], [1, 2, 3]]
    {% endcodeblock %}
　　常用方法：append(x),remove(x),insert(i,x),pop([i]),clear(),copy(),reverse()

### tuple（元组）
　　tuple内容不可修改,immutable  
　　对应符号：()，也可以用tuple()创建。元组的推导式和列表类似，注意把列表的[]换位()即可。


### set（集合）
　　对应符号：{}，也可以用set()创建。其推导式注意两边符号为{},集合的值是单值，注意与dict的区别  
　　常用方法：add(elem),remove(elem),discard(elem),pop(),clear()  
　　使用集合可以方便的求交集、并集、补集，，判断集合的关系等。

### dict
　　对应符号：{}，也可以用dict()创建，其推导式注意两边符号为{}，且内容为{key:value}或{(key,value)}的形式。  
　　常用方法：setdefault(key[,default]),pop(key[,default]),get(key[,default]),keys(),items()

### collections
　　这个模块，实现了特定的数据结构，如namedtuple(),deque(),ChainMap(),defaultdict(),Counter()等。

## 函数式


### map
　　Map将一个函数应用于可迭代对象的每一项。
　　{% codeblock  lang:python  %}
        items = [1,2,3,4,5]
        squared = list(map(lambda x:x**2,items)) # [1, 4, 9, 16, 25]
        #传入一系列的函数
        def multiply(x):
            return (x*x)
        def add(x):
            return (x+x)

        funcs = [multiply, add]
        for i in range(5):
            value = list(map(lambda x: x(i), funcs))
            print(value)

        # Output:
        # [0, 0]
        # [1, 2]
        # [4, 4]
        # [9, 6]
        # [16, 8]
    {% endcodeblock %}

### reduce
　　在可迭代对象上进行计算并返回结果，非常有效
    {% codeblock  lang:python  %}
        #比如你想计算数的乘积
        from functoos import reduce
        product = reduct((lambda x,y:x*y),[1,2,3,4])
        # Output: 24
    {%endcodeblock%}

### filetr
　　对可迭代对象进行过滤
    {% codeblock lang:python  %}
        #比如你只想要负数
        number_list = range(-5, 5)
        less_than_zero = list(filter(lambda x: x < 0, number_list))
        print(less_than_zero)
        # Output: [-5, -4, -3, -2, -1]
    {% endcodeblock %}

## 数值与科学计算

### operator/math/random/itertools

## 多进程多线程

### subprocess
　　
### multiprocessing
　　
### threading
　　注意由于 [Global Interpreter Lock](https://docs.python.org/3/glossary.html#term-global-interpreter-lock "全局锁问题")的原因，实际上thread是顺序执行的，只不过看起来像是同时执行的。如果为了充分利用多核计算机的优势，你应该使用multiprocessing或着concurrent.futures.ProcessPoolExecutor。 

## 正则表达式

### re

## 命令行参数

### argparse

## 日志

### logging

## 网络库

### urllib2
