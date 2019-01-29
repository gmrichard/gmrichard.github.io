---
title: 在Jekyll博客中添加评论系统
layout: post
categories: 开发工具
tags: Jekyll
---



* content
{:toc}



此次添加的评论系统为[gitalk](https://gitalk.github.io/), 基于github issue,很适合github上Jekyll博客。

一. 申请一个OAuth Application
======================================
> Github头像下拉菜单 > Settings > 左边Developer settings下的OAuth Application > Register a new application，填写相关信息：

关键是**Authorization callback URL**，填写和你博客主页地址相同。  

完成后，得到 **Client ID** 和 **Client Secret**，后面需要用到。  

二. 增加关键代码
===============

下载 [gitalk.css]({{'/styles/css/gitalk.css' | prepend: site.baseurl }})
和 [gitalk.min.js]({{'/styles/js/gitalk.min.js' | prepend: site.baseurl }})
放入相应的位置。  

在_layouts下的_post.html中，开始的地方加如下代码：  
<pre>
&lt;link rel="stylesheet" href="../../../../styles/css/gitalk.css"&gt;
    &lt;script src="../../../../styles/js/gitalk.min.js"&gt;&lt;/script&gt;

</pre>


三. 添加评论框代码
=======================
下载[comments.html]({{'/_includes/comments.html' | prepend: site.baseurl }})，放入_includes目录中。  

在那个 _post.html文件中,在正文最后 添加 gitalk 代码,如下:

<pre>
    &lt;!--   gitalk       --&gt;
    
    &lt;div class="comment"&gt;
    &lt;div id="gitalk-container"&gt;&lt;/div&gt;
    &lt;link rel="stylesheet" href="https://unpkg.com/gitalk/dist/gitalk.css"&gt;
    &lt;script src="https://unpkg.com/gitalk/dist/gitalk.min.js"&gt;&lt;/script&gt;
    &lt;script&gt;
    var gitalk = new Gitalk({
        id: '2018-12-27 00:32:24 +0000',
        clientID: '9309266a4518558b7138',
        clientSecret: '3233f9c7e9129249ac3a0e8e04b001cf02220139',
        repo: 'codejsd.github.io',
        owner: 'codejsd',
        admin: ['codejsd'], 
    	labels: ['Gitalk'],
    })
    gitalk.render('gitalk-container')
    &lt;/script&gt;
    
    &lt;/div&gt;
</pre>



四. 添加鉴权代码
==================

在 _config.yml中,最后面,在对应的评论模块添加如下代码:
<pre>
gitalk:
   enable: true
   owner: codejsd
   repo: codejsd.github.io
   clientID: 9309266a4518558b7138
   clientSecret: 3233f9c7e9129249ac3a0e8e04b001cf02220139
   admin: codejsd

</pre>



