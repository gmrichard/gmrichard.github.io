---
title: ubuntu software
layout: post
categories: Ubuntu
tags: Software
---



* content
{:toc}


1\. update source
======================
> find Software & Updates, choose "mirrors.aliyun.com" to the Download Server  
> In Other Software, choose Canonical Partners  
> sudo apt-get update  
> sudo apt-get upgrade  

2\. Sougou Pinyin
===================
> 去[搜狗输入法 for linux](https://pinyin.sogou.com/linux/)下载[sogoupinyin_2.2.0.0108_amd64.deb]({{'/res/files/Software/sogoupinyin_2.2.0.0108_amd64.deb' | prepend: site.baseurl }})  
> 双击安装后 **重启**.  
> 找到Fcitx Configure, 进入点击+号,**Only Show Current Language**前面的勾给去掉, 在下面搜索sougou，然后加入。  

3\. 截图软件 Shutter  
================
> sudo apt-get install shutter  
> **重启**  

4\. 点击图标最小化  
================
> gsettings set org.gnome.shell.extensions.dash-to-dock click-action 'minimize'  

5\. 安装压缩软件  
=================
> sudo apt-get install p7zip-full p7zip-rar rar unzip  

6\. 统一Win10和Ubuntu18.04双系统的时间  
==================================
> timedatectl set-local-rtc 1 --adjust-system-clock  

7\. Chrome Brower  
=======================
> wget -q -O - https://raw.githubusercontent.com/longhr/ubuntu1604hub/master/linux_signing_key.pub | sudo apt-key add  
> sudo sh -c 'echo "deb [ arch=amd64 ] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'  
> sudo apt-get update  
> sudo apt-get install google-chrome-stable  

8\. Tweaks  
===============
> sudo apt-get install gnome-tweak-tool  #安装tweak  
> sudo apt-get install gnome-shell-extensions -y  #安装shell扩展  
> sudo apt install chrome-gnome-shell     #为了能在浏览器内安装gnome插件，火狐和谷歌都能用  
> sudo apt-get install gtk2-engines-pixbuf    #防止GTK2错误  
> sudo apt install libxml2-utils  
>   
> 主题放入: ~/.themes 或 /usr/share/themes  
> 图标放入: ~/.icons 或 /usr/share/icons  

9\. 支持exfat  
=================
> sudo apt-get install exfat-fuse exfat-utils  

10\. 视频和音频  
=====================
> sudo apt --fix-broken install  
> 安装解码器:
> sudo apt-get install ubuntu-restricted-extras  
> 安装VLC视频播放器:  
> sudo apt-get install vlc browser-plugin-vlc   
> 安装FFmpeg:  
> sudo add-apt-repository ppa:djcj/hybrid  
> sudo apt-get update  
> sudo apt-get install ffmpeg  
> 安装网易云音乐:  
> 进入[https://music.163.com/#/download](https://music.163.com/#/download),下载 Ubuntu16.04（64位）。  
> sudo dpkg -i netease-cloud-music\*.deb  
  
11\. adduser
=================
> sudo adduser xxx // xxx is the new user  
> add to sudoers:  
> sudo vim /etc/sudoers  
> root    ALL=(ALL:ALL) ALL  
> shen    ALL=(ALL:ALL) ALL


12\. ssh key
====================
> ssh-keygen -t rsa -b 4096 -C "xxx@xxx.com"  
> ssh -T git@github.com  


13\. 添加删除 PPA 源
========================
> 添加 PPA 源的命令为:  
> sudo add-apt-repository ppa:user/ppa-name  
> 删除命令格式则为：  
> sudo add-apt-repository -r ppa:user/ppa-name  
> 然后进入 /etc/apt/sources.list.d 目录，将相应 ppa 源的保存文件删除

14\. vim
=================
> sudo apt-get install vim  
> cp /etc/vim/vimrc ~/.vimrc

