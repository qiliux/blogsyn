---
title: mxnet安装总结
date: 2017-08-29 15:32:19
tags:
- mxnet
- deep learning
categories:
- mxnet
---
mxnet安装步骤总结，及回顾

核心点
=================
ubuntu默认环境，mxnet官方支持python2 。不要在python3下折腾了(有人是成功的，不过我没有成功。)。

{% note info %}
    2017-08-30 更新： 使用anaconda3 的python3是可以正常使用mxnet的。
{% endnote %}

本人环境
=================

{% note info %} 
elementory os (兼容ubuntu16.04), 1080显卡
{% endnote %} 

安装原则
=================
{% note info %} 
能通过包管理安装的包一律通过包管理安装，如apt-get install package , dpkg -i package.deb
** 只有无可奈何的时候才需要选择下载*.tar.gz之类文件make 安装 **
 这对于你管理电脑的软件有非常大的帮助
{% endnote %} 

安装cuda 8.0
=================
我选择了网络安装的方式，国内有点慢呀。等吧。
{% codeblock lang:Bash %}
sudo dpkg -i cuda-repo-ubuntu1604_8.0.61-1_amd64.deb
sudo apt-get update
sudo apt-get install cuda
{% endcodeblock %}

安装cuDNN
=================

安装显卡驱动
-----------------

{% codeblock lang:Bash %}
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt-get update
sudo apt-get install nvidia-XX(xxe 为 你选择的版本)
{% endcodeblock %}

安装cuDNN runtime
------------------
注册后，下载对应的deb包。 
注意cuda的版本要与cuDNN对应 
{% codeblock lang:Bash %}
sudo dpkg -i libcudnn7_7.0.1.13-1+cuda8.0_amd64.deb
{% endcodeblock %}

验证cuDNNn安装，你需要安装开发包、doc包
{% codeblock lang:Bash %}
sudo dpkg -i libcudnn7-dev_7.0.1.13-1+cuda8.0_amd64.deb
sudo dpkg -i libcudnn7-doc_7.0.1.13-1+cuda8.0_amd64.deb
# 拷贝例子 代码到自己的目录下面
cp -r /usr/src/cudnn_samples_v7/ /data1/mxnet-learn/cudnn-sample
# 进入自己的代码目录
cd /data1/mxnet-learn/cudnn-sample
# 使用cuDNN
make clean && make
./mnistCUDNN
# 然后你看到Test passed 就成功了
{% endcodeblock %}

安装virtualenv
===================

{% codeblock lang:Bash %}
sudo apt-get update
sudo apt-get install -y python-dev python-virtualenv
{% endcodeblock %}

创建virtualenv mxnet虚拟环境
==============================
{% codeblock lang:Bash %}
virtualenv --system-site-packages ~/mxnet
source ~/mxnet/bin/activate
pip install --upgrade pip
# 我用的是GPU版本
pip install mxnet-cu80==0.11.0.rc3
{% endcodeblock %}


安装graphviz
==============================
{% codeblock lang:Bash %}
sudo apt-get install graphviz
pip install graphviz
{% endcodeblock %}

运行mxnet例子，测试安装
=============================
{% codeblock lang:Bash %}
# 记住启用创建的mxnet虚拟环境
source ~/mxnet/bin/activate
vi test.py
{% endcodeblock %}

输入以下代码
{% codeblock lang:python %}
import mxnet as mx
a = mx.nd.ones((2, 3), mx.gpu())
b = a * 2 + 1
print b.asnumpy()
{% endcodeblock %}

结果如下
{% codeblock lang:Bash %}
array([[ 3.,  3.,  3.],
       [ 3.,  3.,  3.]], dtype=float3
{% endcodeblock %}


