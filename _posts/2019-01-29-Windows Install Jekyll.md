---
title: Windows Install Jekyll
layout: post
categories: Windows
tags: Software Jekyll
---



* content
{:toc}



  

1. 下载 Ruby+Devkit  
   官方网站 [https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/) ,  
   需要下载RubyInstallers WITH DEVKIT 的版本.
   
2. 安装RUBY环境  
   安装完后,通过如下命令测试是否安装成功:  
> ruby -v  
> gem -v
	
3. 安装jekyll  
> gem install jekyll  
> jekyll -v  

4. 安装bundle  
> gem install bundle  

5. 生成blog  
> jekyll new myblog  

没有报错的话，jekyll安装完成。



