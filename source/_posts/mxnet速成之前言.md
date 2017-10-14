---
title: mxnet速成前言
date: 2017-08-30 09:37:32
tags:
- mxnet
- deep learning
categories:
- mxnet
---

前言
===============
如果你是正常人，你可能会问：什么是 mxnet-the-straight-dope? 你可能也会问为什么它拥有这么一个华丽盛大的名字？
回答地一个问题：mxnet-the-straight-dope尝试创造一种新的深度学习的教学资源。我们的目标是利用Jupyter notebook的长处，在一个地方同时展示文章、图片、公式、代码（及其重要）。如果我们成功的话，最后形成的资料将同时成为一本书、课程教材、所见即所得的教程、参考有用代码的地方。据我们所知,很少有资料致力于讲述现代机器学习概念的广度的概念，同时交错包含着一份优秀的可运行的代码。在这次冒险的终点，我们将发现是否void(指这样即包含文章又包含代码的资料？)有存在的理由。

关于名字，我们已经认识到我们经营的机器学习社区和生态系统已经步入到了荒诞的地步。在20实际初，机器学习领域相对较少的任务已经被解决了，但是我们感觉我们已经理解了这些模型怎么做和为什么那么做（在一定的条件下）。相反来说，今日的机器学习系统是非常的强大，但大量的问题仍然是为什么他们就是那么高效。

新的世界充满巨大的机遇，但仍然导致了相当数量的滑稽情况。Research preprints have been flooded by clickbait, AI startups have sometimes received overly optimistic valuations, and the blogosphere is flooded with thought leadership pieces written by marketers bereft of any technical knowledge.在充满嘈杂、大量的资金、松散的标准的现实下，我们坚信不把我们的模型放在他们过度崇拜的环境之中，是非常重要的。同时，为了同时解释、可视化、构造全面广度的模型（这些是我们尝试去声明、表达的），作者在写作的过程不会无聊也很重要。

组织方式
===============
当前，我们倾向于下面的格式：除了少数的notebook提供了速成的方案，每一个后续的notebook都会包含：

1. 介绍合理数量的新概念
2. 用一个真实的数据集，提供一个自我可运行工作的例子

当需要的时候，同时会提供一个背景材料。那就是说，我们经常在充分解释概念之前，先使工具可用（我们随后跟进会解释背景）。举个例子，在充分解释为什么随机梯度下降是有用的之前，我们会使用Stochastic Gradient Descent（随机梯度下降）。至少在短期内，以读者做决定充分相信mxnet的情况下，这会给予从业者充分的工具去快速的解决问题。从头到尾，我们都将使用mxnet库。mxnet库是一个对于研究来讲拥有难得的灵活性，同时对于生产环境足够fast.我们通常都会使用MXNET新的势在必行的高级接口<span class='inline-label'>gluon</span> 。注意他和<span class='inline-label'>mxnet.module</span>不同，<span class='inline-label'>mxnet.module</span>是一个MXNET支持的老的、symbolic的接口。

通过动手来学习
===============
很多的书籍都会教一系列的内容，每一个都是详细的描述。比如，Chrips Bishp的杰出的书籍《 Pattern Recognition and Machine Learning 》，把每个主题都讲的非常透彻，导致阅读理解 <span class='inline-blue'>linear regression </span>时，需要花费相当大的工作量。当我第一次学习machine learning的时候，作为一本入门书，这实际上限制了这本书的用处。在很多年之后，当我重新阅读的时候，恰恰因为他的透彻详细，我喜欢这本书。但此刻，我仍然无法想象作为第一本书来进行学习。

实际上，在我们这本中，我们会及时的介绍大多数的概念。对于基础的先须知识，比如linear algebra、probability，我们会一开始就提供简单的速成课程，但是我们希望你在过度担心exotic probability distributions 之前先体验训练你地一个模型的感觉。

下一步
===============
如果你已经打算开始了，或者访问我们的 [TOC](http://gluon.mxnet.io/) 或者直接开始 [基础NDArray操作]() MXNET的基础数据结构

学习的单词
==========
```
dope : 麻醉剂， 笨蛋，
ostentatious :  表面上的，华美的，过于盛大的
interleave ： 交错
engaging ： 优胜
lurch ： 踉
absurd ： 荒诞
comparatively ： 比较
conquer ： 征服
caveat ： 注意事项
precisely ： 恰恰，就是
enormous ： 巨大
buffoonery ： 滑稽
bereft ： 丧失
Amid ： 在一片，在什么之中
worshipe ： 崇拜
subsequent ： 后续
ammunition ： 弹药
exhaustive ： 详细
thoroughly ： 透彻
preliminaries ： 初步措施, 初步行动
satisfaction ： 满足
exotic ： 	异, 傀
linear algebra ： 线性代数
workhorse ： 驮马
``` 