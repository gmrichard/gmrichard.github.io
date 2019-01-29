---
title: sublime-text 3
layout: post
categories: Ubuntu
tags: Software
---



* content
{:toc}



<pre>
tips: 
apt-get install 安装所下载的软件包在: 
/var/cache/apt/archives
sudo dpkg -i xxx.deb  // 安装软件包
</pre>

1\. sublime-text 3
======================
官网：
> [http://www.sublimetext.com/](http://www.sublimetext.com/)  

apt-get Install:
> wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -  
> sudo apt-get install apt-transport-https  
> echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list  
> echo "deb https://download.sublimetext.com/ apt/dev/" | sudo tee /etc/apt/sources.list.d/sublime-text.list  
> sudo apt-get update  
> sudo apt-get install sublime-text  

package:  
> [sublime-text-3.1.1_3176]({{'/res/files/Software/sublime-text_3176_amd64.deb' | prepend: site.baseurl }})  

sublime-text-3.1.1_3176 serial:
<pre>
----- BEGIN LICENSE -----
sgbteam
Single User License
EA7E-1153259
8891CBB9 F1513E4F 1A3405C1 A865D53F
115F202E 7B91AB2D 0D2A40ED 352B269B
76E84F0B CD69BFC7 59F2DFEF E267328F
215652A3 E88F9D8F 4C38E3BA 5B2DAAE4
969624E7 DC9CD4D5 717FB40C 1B9738CF
20B3C4F1 E917B5B3 87C38D9C ACCE7DD8
5F7EF854 86B9743C FADC04AA FB0DA5C0
F913BE58 42FEA319 F954EFDD AE881E0B
------ END LICENSE ------
</pre>

禁用 sublime Text 3 新版本检测:  
> Preferences -> Settings-User  
> "update_check": false  




