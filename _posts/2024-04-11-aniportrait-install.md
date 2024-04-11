---
layout: post
title: 干货教程【AI篇】|腾讯开源数字人工具AniPortrait整合包获取和使用教程
categories: [AI数字人]
description: 腾讯开源数字人工具AniPortrait整合包获取和使用教程
keywords: AniPortrait, 数字人, AI
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
topmost: false
---

最近腾讯开源了一款数字人工具，直接对标阿里的EMO，github 地址为：<https://github.com/Zejun-Yang/AniPortrait>
主要支持以下两个功能：

1. 脸部重演
通过给定一段视频和一张图片，可以把视频中的人物替换为图片中的人物，支持二次元人物
2. 音频驱动
通过给定一张人物照片和一段音频，生成一段语音和嘴型同步的视频，支持二次元人物

**电脑配置和环境要求**

- 系统要求： windows 10 或者11
- 显卡要求： 英伟达独立显卡，俗称N卡，要安装好显卡驱动, 显存8G及以上
- 内存要求：16G及以上
- 硬盘要求： 要有至少30G左右的剩余存储空间，最好是固态硬盘

**本文章主要分为两部分：**

 1. 详细介绍 AniPortrait 源码运行环境搭建
 2. 详细介绍 AniPortrait 如何使用。

由于源码运行环境搭建较为复杂，觉得麻烦的小伙伴可以跳过第一部分，直接下载我为大家准备的整合包，然后按照文章第二部分使用教程操作即可。

*[点击打开我的个人博客网站](https://koalai.org/about/)扫码或者搜索关注公众号**树袋熊AI**，并回复关键词【**AniP**】获取包含模型的整合包*

## 1.  AniPortrait 源码运行环境搭建

### 基础软件安装

显卡驱动、cuda、git、ffmpeg、anaconda安装这些我就不再详细介绍了，可以参考[Rope源码运行环境搭建这篇博客](https://blog.csdn.net/qq_17449077/article/details/137027934)去安装这些基础软件。另外如果是window10/11的小伙伴可以使用 winget 在终端安装这些软件更加方便，可以在终端通过 “winget search 软件名字” 去搜素，复制id后通过 “winget install 软件id” 去安装。

### 源码下载及运行环境搭建

打开Power Shell终端，按照以下步骤运行，注意windows下不要拷贝带#的注释

```bash
# 1. 下载源码，clone失败的话，可以去github下载压缩包解压代替这一步
git clone https://github.com/Zejun-Yang/AniPortrait.git
# 2. 进入源码文件夹
cd AniPortrait
# 3，创建conda虚拟环境
conda create -n AniPortrait python=3.10
# 4，激活虚拟环境
conda activate AniPortrait
# 5. 安装软件运行所需的依赖库
pip install -r requirements.txt
```

### 下载和放置模型

从下面的5个地址中下载模型，并放到 pretrained_weights 文件夹中：
[weights](https://huggingface.co/ZJYang/AniPortrait/tree/main)
[StableDiffusion V1.5](https://huggingface.co/runwayml/stable-diffusion-v1-5)
[sd-vae-ft-mse](https://huggingface.co/stabilityai/sd-vae-ft-mse)
[image_encoder](https://huggingface.co/lambdalabs/sd-image-variations-diffusers/tree/main/image_encoder)
[wav2vec2-base-960h](https://huggingface.co/facebook/wav2vec2-base-960h/tree/main)

所有的模型我已经下载打包好了，获取方式在文末。下载完成后最终模型目录如下：
![在这里插入图片描述](/images/2024-04-11-aniportrait-install/799097e729e14f82b8f6ab0349c11ac0.png)

### 运行AniPortrait 源码

打开Power Shell终端运行，注意windows下不要拷贝带#的注释

```bash
# 1. 进入源码文件夹
cd AniPortrait
# 2，进入虚拟环境
conda activate AniPortrait
# 3. 运行代码进行推理, 运行成功后终端会出现一个url链接，浏览器打开链接即可 
python -m scripts.app 
```

运行后如果终端报缺失 dll 的错误，请到文末获取 VC_redist 并安装

## 2. AniPortrait 使用教程

运行成功后，浏览器打开 url 程序主界面如下：
![在这里插入图片描述](/images/2024-04-11-aniportrait-install/864acce41991414a9001ae19dc500698.png)

默认的处理序列长度L是60，比较短，建议修改成0，表示会自动计算序列长度，W和H表示输出视频的长度和宽度，尽量不要调整太高，建议用默认的值，如果想得到高清视频，可以用视频增强软件去处理。

可以上传自己本地的数据，另外 examples 中也自带了一些测试数据，点击后会自动加载到上传区，点击Generate等待视频生成即可，Result 中会显示最终生成的结果，可以播放或者下载到本地。

我测试了一下，感觉除了最后几帧效果会比较差，整体效果还不错。

*[点击打开我的个人博客网站](https://koalai.org/about/)扫码或者搜索关注公众号**树袋熊AI**，并回复关键词【**AniP**】获取包含模型的整合包*
