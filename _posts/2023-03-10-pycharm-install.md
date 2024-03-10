---
layout: post
title: 干货教程【软件篇】| windows 下如何快速安装使用Pycharm IDE进行Python开发
categories: [Python]
description: 干货教程【软件篇】| windows 下如何快速安装使用Pycharm IDE进行Python开发
keywords: Python, Pycharm, Conda, AI, 人工智能
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
topmost: false
---
PyCharm是一款由JetBrains开发的Python集成开发环境（IDE）。它为Python开发提供了全面的支持，包括代码编辑、调试、代码分析、版本控制集成等功能。非常适合刚学习Python的小白进行开发，不用像VS Code 那样需要进行复杂的json配置。

如果你还没有安装配置Python环境，建议先看上一篇去安装一下Python环境，你可以选择安装系统Python或者Miniconda或者Anaconda集成的python环境，对于初学者建议安装Miniconda。[点我进入Python安装配置教程](https://koalai.org/2024/03/09/python-install/)

## Pycharm 免费版怎么下载
JetBrains 公司提供了Pycharm 完全免费的社区版（Community）和收费的专业版（Professional），对于普通开发人员来说，社区版完全够用了。但如果你进入[Pycharm 官网](https://www.jetbrains.com.cn/pycharm/)，点击主页下载的将会是专业版，试用一段时间后就会收费，其社区版隐藏的比较深，这里我直接给出社区版本的的下载链接 ：[下载社区版请点击我](https://www.jetbrains.com.cn/pycharm/download/other.html)。选择对应的版本，点击即可下载
![在这里插入图片描述](/images/2023-03-10-pycharm-install/ltlhcuqu90.png)

## Pycharm 怎么安装
安装的话就比较简单，建议不要安装在C盘，另外需要注意勾选添加Pycharm的bin目录到环境变量，以及关联.py文件，第一次安装的小伙伴，可以看下详细安装步骤：
1. 双击打开刚下载的pycharm 安装包，是以exe为后缀的，很多小伙伴表示自己的文件名怎么没有后缀，图中的文件扩展名前面有对勾了，表示是打开了文件扩展，这样我们就能清楚的看到这个文件的类型，这里建议大家把文件扩展名的设置打开。
![在这里插入图片描述](/images/2023-03-10-pycharm-install/ltlhcwcd91.png)
2. 打开之后点击下一步，到设置安装路径界面，建议非系统盘（大部分系统盘都是C盘），点击下一步
![在这里插入图片描述](/images/2023-03-10-pycharm-install/ltlhcxxt78.png)
3. 进入到了设置安装选项界面，这里建议把四个都勾选上，尤其是更新PATH和创建关联两个选项，点击下一步，再点击安装，等待安装完成
![在这里插入图片描述](/images/2023-03-10-pycharm-install/ltlhczih85.png)
4. 安装完成后，会让你选择是否重启系统，如果不重启的话，就是PATH变量的设置不会生效，这在我们在终端用bin目录下的一些工具时才会有影响，正常写代码没啥影响，我们可以暂时选择不重启就行，然后点击完成就安装好了
![在这里插入图片描述](/images/2023-03-10-pycharm-install/ltlhd15455.png)

## Pycharm怎么配置使用

### 一. 如何创建新的Python工程
1. 双击安装好的Pycharm，第一次运行会让你勾选协议，然后点击Continue，进入到打开项目的界面，你可以打开已有的项目（点击Open），也可以新建一个项目（点击 New Project），这里我以新建一个项目为例
![在这里插入图片描述](/images/2023-03-10-pycharm-install/ltlhd2pt68.png)
2. 设置项目的名字（Name），一定要是英文；设置项目的位置（Location），这将会在这个路径下创建一个以项目名字命名的文件夹，勾选Create a main.py，这个可选可不选；设置python解释器，这里我建议先不设置，稍后再设置，即选择自定义Custom environment、Select existing、type选择Python、Python path里面先不填。然后点击Create
![在这里插入图片描述](/images/2023-03-10-pycharm-install/ltlhd4b206.png)
3. 创建完成后就打开了我们的项目，此时我们的项目还空空如也，我们可以新建一个Python文件，设置文件名，最好是英文（ps: 作为开发者，我们的所有文件和文件夹名字最好都是英文，中文在某些场景会出现意想不到的问题），这里我设置了一个名为test的文件，demo文件下就会生成一个test.py文件，后缀.py表示这是一个Python文件，但此时我们还没有设置Python的解释器，右下角显示了No interpreter，此时我们在这个文件下面写代码也没有自动提示，所以先要设置下解释器
![在这里插入图片描述](/images/2023-03-10-pycharm-install/ltlhd5wu03.png)![在这里插入图片描述](/images/2023-03-10-pycharm-install/ltlhd7hx62.png)

### 二. 如何设置Python解释器
1. 点击左上角导航栏的File，然后点击Settings
![在这里插入图片描述](/images/2023-03-10-pycharm-install/ltlhd93382.png)
2. 点击选择Project:Demo项目，然后在右边的界面中选择Python Interpreter
![在这里插入图片描述](/images/2023-03-10-pycharm-install/ltlhdao384.png)3. 如果路径为No Iterpreter就表示没有解释器，点击Add Interpreter，设置解释器
   + 如果你是安装的Miniconda或者Anaconda，那可以去按照下图中的步骤依次设置已存在的conda 环境，
![设置已存在的conda环境](/images/2023-03-10-pycharm-install/ltlhdc8v52.png)
	+  如果你是直接安装的官方的Python，即系统Python，可以按照下图设置已存在的系统Python解释器
![在这里插入图片描述](/images/2023-03-10-pycharm-install/ltlhddw372.png)
ps: 如果两种都安装了我比较建议去用conda 的环境
3. 设置完成后点击ok，会加载环境中已经安装的三方库，再点击ok安装Python 解释环境的设置
![在这里插入图片描述](/images/2023-03-10-pycharm-install/ltlhdfgy20.png)

### 三. 如何编写运行Python代码
1. 在新建的test.py中粘贴以下测试代码
	```python
	# 加法
	def add(a, b):
	    print(a + b)
	
	
	if __name__ == '__main__':
	    add(1, 2)
	 ```
2. 选中test.py，点击右键，然后选择点击run 'test'，运行代码，最下面的控制台输出了3，表示我们的代码运行成功了
![在这里插入图片描述](/images/2023-03-10-pycharm-install/ltlhdh1m64.png)
