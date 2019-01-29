---
title: Android Studio for Linux 版本安装
layout: post
categories: Android
tags: 'android studio'
---



* content
{:toc}




1\. 下载Android Studio  
> 去[http://www.android-studio.org/](http://www.android-studio.org/)下载linux版本.  
> unzip android-studio-ide-181.5014246-linux.zip  
> sudo mv android-studio /opt/  

2\. 运行  
> cd /opt/android-studio/bin/  
> sudo ./studio.sh  

3\. Failed to load module "canberra-gtk-module"  
> sudo apt-get install libcanberra-gtk-module  

4\. unable to access android sdk-on list  
> 1) Cancel, 后续的界面再安装SDK.  
> 2) 打开/Android Studio/bin/idea.properties; 最后面添加上这句话：disable.android.first.run=true  




