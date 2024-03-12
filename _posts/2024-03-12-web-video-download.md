---
layout: post
title: 干货教程【软件篇】| IDM+m3u8解析工具无脑下载非主流网站视频
categories: [ChatGPT]
description: 干货教程【软件篇】| IDM+m3u8解析工具无脑下载非主流网站视频
keywords: IDM, m3u8, 下载视频, 网站
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
topmost: true
---
当你浏览一个网站，看到一个喜欢的视频，不知道如何下载的时候，本教程或许可以帮你点小忙。大部分的主流网站都有专门的下载工具，本篇教程主要针对的是一些非主流的小网站。

我们的下载方法就是利用IDM的嗅探功能，自动获取视频的链接并去下载，对于有些网站可能会下载失败，但此时IDM已经获取到了m3u8的地址，我们可以利用m3u8解析工具去下载下来。

由于IDM只支持windows系统，所以本教程不适应于Linux或者Mac，后续我也会更新一些支持多平台的下载工具，以及一些主流网站的下载教程，欢迎大家持续关注。

**文末附上了IDM和m3u8解析工具的获取方式**，第一次使用的小白可以往下细看一下安装使用教程

## IDM是什么
Internet Download Manager（IDM），拥有强大的**多线程下载功能**，可以极大地提高下载速度。它支持多种协议，包括HTTP、HTTPS、FTP等，**并能自动捕获浏览器中的下载链接**，实现一键下载。此外，IDM还具有**断点续传功能**，即使在网络不稳定的情况下，也能保证下载任务的顺利进行。

IDM功能虽然强大，但是是收费的，网上有很多免激活版的，但是由于IDM管控的越来越严，用一段时间就**失效或者出现弹窗问题**。我提供的这一版，用了半年还没出现上述问题，欢迎大家到文末下载。

## IDM怎么安装

1. 获取到安装包后，在解压之前请关闭所有杀毒软件和windows安全中心，如果你的目录与我的不一致，可能是杀毒软件删除了某些文件，请一定关闭，重新解压，然后双击打开安装程序
![alt text](/images/2024-03-12-web-video-download/image.png)

2. 默认选择，即选择Standard Installation of the program，点击Next
![alt text](/images/2024-03-12-web-video-download/image-1.png)

3. 继续默认选择，点击Next
![alt text](/images/2024-03-12-web-video-download/image-2.png)

4. 设置安装的路径，最好不要安装在系统盘（通常为C盘），点击Next
![alt text](/images/2024-03-12-web-video-download/image-3.png)

5. 默认选择即可，点击Next
![alt text](/images/2024-03-12-web-video-download/image-4.png)

6. 默认选择，点击Next，等待安装完成
![alt text](/images/2024-03-12-web-video-download/image-5.png)

7. 安装完成后，我们还需要在浏览器中安装一个插件，最好是Edge或者Google浏览器，这里我以Edge浏览器为例，进入[Edge插件商店](https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home)，搜索IDM，选择 IDM Integration Module，点击获取安装这个插件，安装完成后重启浏览器
![alt text](/images/2024-03-12-web-video-download/image-6.png)

## IDM 怎么使用

这里我以下载[这个站点](https://www.bjjnhzs.com/play/568807-2-1/)的视频为例，打开视频右上角会有一个【下载该视频】的按钮，点击它，会弹出下载的设置，设置下载路径，确认下视频时常，点击Start Download就可以下载了
![alt text](/images/2024-03-12-web-video-download/image-7.png)

## IDM下载失败怎么办

   **如果下载的时候弹出如下错误，或者是视频是分段的，下载比较麻烦，你可以尝试使用m3u8解析工具下载**
![alt text](/images/2024-03-12-web-video-download/image-8.png)
![alt text](/images/2024-03-12-web-video-download/image-9.png)

在使用m3u8下载之前我们需要从IDM中获取m3u8地址，打开IDM软件，选择刚才下载失败的记录，点击鼠标右键，再点击Properties, Address中的地址即为m3u8地址，复制即可
![alt text](/images/2024-03-12-web-video-download/image-10.png)

## m3u8解析工具的安装和使用

**安装包我放在文末了，直接解压就可以用了，绿色版免安装的**

双击打开 N_m3u8DL-CLI_v3.0.2.exe 程序，粘贴m3u8地址，填写视频标题（不包含后缀）
   建议设置合并后删除分片，点击GO下载就可以，这个下载速度是很快的
![alt text](/images/2024-03-12-web-video-download/image-11.png)


**关注微信公众号：$\color{#FF00FF} 树袋熊AI $**，回复【**IDM**】获取安装包

**关注微信公众号：$\color{#FF00FF} 树袋熊AI $**，回复【**IDM**】获取安装包