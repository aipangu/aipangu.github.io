---
layout: post
title: 干货教程【软件篇】--如何在Windows上安装Python环境以及设置国内源（Miniconda/Anaconda安装）
categories: [Python]
description: 干货教程【软件篇】--如何在Windows上安装Python环境以及设置国内源（Miniconda/Anaconda安装）
keywords: Python, AI, 人工智能
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
topmost: false
---
**小白安装前须了解一下**
* Python解释器是用来解释运行我们编写的Python代码。
* Python标准库是Python自带的一系列标准模块，提供了各种基础功能。
* Python第三方库（包）则是由Python社区开发的扩展模块，用于增强Python的功能。由于三方库众多，我们可以用包管理工具来管理这些三方库。常见的有pip、conda、easy_install等
* Python编辑器或IDE是用于编写和编辑Python代码的软件工具，常见的Python编辑器或IDE有Visual Studio Code、PyCharm等。
* Python虚拟环境，用于隔离不同项目的依赖关系，避免不同项目之间的冲突。虚拟环境可以使用工具如venv或conda来创建和管理，不同虚拟环境中可以有不同版本的Python、标准库和三方库。

我们可以从Python官网下载安装Python环境(需要科学上网)，也可以直接安装Miniconda或者Anaconda。Miniconda和Anaconda的区别在于Miniconda比较轻量化，主要是conda、python解释器和标准库这些东西，Anaconda比较大，会安装一堆常用的三方库以及IDE等。这里我推荐安装Miniconda，需要什么三方库我们再去下载安装就可以。

## 官网安装Python环境（初学者不太推荐）
官网下载Python需要科学上网，否则网速贼慢。首先查看自己电脑的系统类型，以window11为例，进入设置->系统->系统信息->设备规格->系统类型中可看到自己的系统位数，点击[下载链接](https://www.python.org/downloads/windows/)进入选择对应的版本进行下载
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/b2a49fe9ae3840a9a032e2014e5cd13a.png)
下载完成后，双击打开，勾选Add python.exe to PATH，点击Install Now，即可完成安装
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/ec42ae0660ff43a0b619d2bea6c3b5b9.png)
测试是否安装成功，打开Window PowerShell，输入Python -V显示版本号即为安装成功
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/62b21172f57a4c9ca479ec353e150f78.png)

## 基于Miniconda/Anaconda安装Python环境（小白极力推荐）

由于某些限制，Miniconda官网很难进入，这里给出国内镜像的[下载地址](https://mirrors.bfsu.edu.cn/anaconda/miniconda/)，往后滑直接选择前缀是”Miniconda3-py”的，点击下载
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/99b0d98d7b424eacbbd247c462ee8e4a.png)
双击打开后依次选择"Next"->"I Agree"->"Next"，设置安装路径
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/3afce6613956417c8cd169612beb0e86.png)
然后点击"Next"->"Install"等待安装完成，点击”Next“->"Finish"即可完成安装，安装完成后在应用中打开Anaconda Prompt，依次输入conda -V和python -V，版本号正常显示即为安装成功。
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/9bcff483fa384e2c819aedbb6b5027c3.png)
Miniconda会默认建立名字为base的虚拟环境，所以终端前面会带一个（base），表示我们目前进入到了base这个虚拟环境中。在Anaconda Prompt中执行以下命令可进入或者退出base虚拟环境。
```bash
# 进入base环境
conda activate base
# 退出当前环境
conda deactivate
```
基于Anaconda安装Python环境的安装步骤Miniconda基本一致，这里我就不再详述了。点击[下载链接](https://www.anaconda.com/download)进入Anaconda的官方下载网站，点击Download进行下载，可以看到Anaconda比Miniconda大的多。

## conda 配置国内源
conda可以用来管理虚拟环境和三方库，但是国内在安装这些三方库的时候会非常慢，甚至安装到一半就断开，所以配置国内的镜像源是非常有必要的，这里以清华源为例，在Anaconda Prompt中执行以下命令添加清华源
```bash
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge 
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
conda config --set show_channel_urls yes
```
如果要恢复到默认源，可以执行以下命令
```bash
conda config --remove-key channels
```
conda 安装三方库的命令如下，这里以numpy库为例
```bash
conda install numpy -y
```
安装完成后执行如下命令，查看是否安装成功
```bash
conda list
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/790a497d3b2046efb94f7d732e299b7a.png)

## pip设置国内源
以清华源为例，打开Window PowerShell，执行以下命令即可
```bash
pip3 install pip -U
python -m ensurepip 
python -m pip install --upgrade pip
pip3 config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/0621559c9a01413586a34ad218ed8f96.png)
运行如下命令安装numpy库
```bash
 pip3 install numpy
```
执行以下命令查看安装是否成功
```bash
pip3 list
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/1ff2850072d74f5f9590f6a3eae897b2.png)
安装包我已经打包好了
下载地址：https://url88.ctfile.com/d/54203788-60316438-32fd29?p=2573 (访问密码: 2573）