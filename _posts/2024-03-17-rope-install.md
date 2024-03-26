---
layout: post
title: 干货教程【AI篇】| AI换脸软件Rope搭建环境运行源码详细教程
categories: [AI换脸]
description: AI换脸软件Rope搭建环境运行源码详细教程
keywords: Rope, AI换脸, AI
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
topmost: false
---

Rope 是一个免费开源的 AI 换脸软件，它具有图形化界面，使得甚至小白也能够轻松地进行简单的操作。该软件提供了多种高清化算法，使用者可以实时观察换脸效果，并且还支持多种遮罩模式以及将多个人脸一起融合的功能。Rope 的官方 GitHub 仓库地址为：https://github.com/Hillobar/Rope

网上也有一些Rope的整合包，免去了小白配置环境困难的苦恼，如果你觉得配置Rope的运行环境比较麻烦，可以直接跳到文章后半部分看Rope的使用教程即可。Rope整合包我也打包了一份，可以关注我的微信公众号进行下载
但我个人还是推荐你自己部署一下环境，有以下几点好处：
1. 市面上的AI工具层出不穷，更新速度极快，如果你想搭上AI这趟顺风车，那学会配置环境是必不可少的，也就能够去配置使用Github上其他的开源AI工具，毕竟不是每一个开源AI工具都是有整合包的。
2.  Rope是在不断更新的，如果你自己配置的环境，只用通过几行简单的命令就能更新到最新版本，而不用等着别入去给你整合最新版本的安装包
3. 配置环境也是个学习的过程，你也能够了解到使用这个AI工具需要的一些依赖，有助于解决运行过程中出现的一些问题。如果你使用的是整合包，那么在遇到软件运行上的一些问题时你可能无从下手。

如果你是一个IT技术人员，那么直接去参考官方安装教程即可：https://github.com/Hillobar/Rope/wiki

如果你是一个小白，可以看我下面的更为详细的教程

 *Rope的整合包需要的小伙伴可以[点击打开跳转到我的博客](https://koalai.org/about/)，关注微信公众号，回复关键词【**rope**】获取。*

整合包详细使用教程参考之前写的[这篇博客](https://blog.csdn.net/qq_17449077/article/details/136782719)
## Rope环境配置和安装

1. 安装Miniconda
如果你的电脑上还没有conda 环境，可以[参考我之前的文章](https://blog.csdn.net/qq_17449077/article/details/136519192)去安装conda环境，建议安装Miniconda即可。安装完成后需要设置conda路径到系统环境变量，首先在开始菜单搜索**环境变量**，打开**编辑系统环境变量**
![在这里插入图片描述](/images/2024-03-17-rope-install/lu8l8tje67.png)
然后按照以下步骤添加conda 到系统环境变量中，我的路径是：D:\miniconda3\Scripts
![在这里插入图片描述](/images/2024-03-17-rope-install/lu8l8v4j73.png)
	我们所有的命令都是在Anaconda Prompt 终端执行的，首先需要打开这个终端

	如果你想在window Power Shell中执行，那么需要在第一次运行conda时执行如下命令：
	```bash
	conda init powershell
	```
	如果你想到在cmd 中执行，那么你需要第一次运行conda时执行如下命令
	```bash
	conda init cmd.exe
	```
2. 下载源码 
	首先打开[git官网](https://git-scm.com/download/win)下载并安装git ，然后下载Rope源码，即执行以下命令。如果你clone的时候失败，可以直接去github下载源码压缩包，解压即可。
	```bash
	git clone https://github.com/Hillobar/Rope #clone失败可以下载压缩包解压即可
	```
	然后需要进入到源码所在目录（请根据自己的情况替换路径）。即执行以下命令
	```bash
	cd Desktop\github_proj\Rope
	```
		
4. 配置python环境和依赖
	Rope要求的python 版本是3.10，首先需要使用conda去新创建一个环境，并指定python版本。即执行以下命令：
	```bash
	conda create -n Rope python=3.10.13 -y
	```
	然后需要进入新创建的环境。即执行以下命令
	```bash
	conda activate Rope
	```
	最后安装需要的依赖包。即执行以下命令
	```bash
	python -m pip install -r requirements.txt
	```
5. 安装ffmpeg
	ffmpeg windows版[官网下载地址](https://www.gyan.dev/ffmpeg/builds/)，下载以git-full为后缀的
![在这里插入图片描述](/images/2024-03-17-rope-install/lu8l8wpl60.png)

	下载完成后解压压缩包，复制bin目录路径
![在这里插入图片描述](/images/2024-03-17-rope-install/lu8l8yay57.png)

	依次按照以下步骤，把bin路径添加到系统环境变量中
![在这里插入图片描述](/images/2024-03-17-rope-install/lu8l8zw064.png)
	设置完成后打开终端，输入以下命令验证
	```bash
	ffmpeg -version
	```
	如果显示如下，则说明ffmpeg安装成功
![在这里插入图片描述](/images/2024-03-17-rope-install/lu8l91hv12.png)

5. 安装cuda
	[点击进入cuda官方下载地址](https://developer.nvidia.com/cuda-toolkit-archive)
	点击进入，Rope要求下载11.8.0版本的，双击打开此版本
![在这里插入图片描述](/images/2024-03-17-rope-install/lu8l933e41.png)

	按照如下图所示选择，点击Download进行下载
![在这里插入图片描述](/images/2024-03-17-rope-install/lu8l94ot69.png)
	下载完成后安装，双击打开，设置安装路径，依次默认安装即可。安装完成后输入以下命令
	```bash
	nvcc -V
	```
	如果显示如下，则安装成功
![在这里插入图片描述](/images/2024-03-17-rope-install/lu8l969r80.png)

6.  安装cudnn
[打开cudnn官方下载地址](https://developer.nvidia.com/cudnn-downloads)，按照下图选择，点击Download进行下载
![在这里插入图片描述](/images/2024-03-17-rope-install/lu8l97um54.png)
下载完成后解压，目录如下，全选，然后全部复制
![在这里插入图片描述](/images/2024-03-17-rope-install/lu8l99ft36.png)
进入这个路径C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8，粘贴刚才复制的所有文件到这下面即可完成安装

## Rope运行和使用

第一次运行的时候需要进行初始化配置，之后双击Rope.bat就可以运行使用了
### Rope初始化配置
1. 在Rope文件夹下新建三个文件夹：videos用于存放需要被换脸的视频；faces用于存放需要换脸的图片；output存放换后的结果。

3. [点击进入](https://github.com/Hillobar/Rope/releases/tag/Sapphire)这个网站下载所有模型，并放到Rope/models中，目录如下
	![在这里插入图片描述](/images/2024-03-17-rope-install/lu8l9b0g47.png)

4. 修改Rope.bat，用记事本打开，复制替换以下内容到Rope.bat文件中
	```
	call conda activate Rope
	python Rope.py 
	pause
	```
4. win+r 输入cmd打开终端，输入以下命令回车
	```bash
	conda init cmd.exe
	```
## 运行Rope
	
双击Rope.bat，不出意外的话会弹出如下界面，图中三个位置对应设置为刚才创建的三个文件夹
![在这里插入图片描述](/images/2024-03-17-rope-install/lu8l9cls07.png)
详细使用教程参考之前写的[这篇博客](https://blog.csdn.net/qq_17449077/article/details/136782719)
