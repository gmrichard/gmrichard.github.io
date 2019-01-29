---
title: git命令
layout: post
categories: 开发工具
tags: git
---



* content
{:toc}




远程仓库命令
==============
1. clone
> git clone git@github.com:codejsd/lm.git
2. 查看远程仓库
> git remote -v
3. 添加远程仓库
> git remote add [name][url]  
> 例子：git remote add origin git@github.com:codejsd/lm.git
4. 删去远程仓库
> git remote rm [name]  
> 例子：git remote rm origin
5. 修改远程仓库
> git remote set-url [name][newUrl]
6. 增加远程仓库分支
> git push [name] [branch]  
> 例子：git push origin gh-pages
7. 删去远程仓库分支
> git push [name] :[branch]  
> 例子：git push origin :gh-pages  
8. 拉取远程仓库
> git pull origin master


基本命令
============
1. 查看本地修改状态
> git status
2. 添加更新
> git add .
3. 提交更新
> git commit -m "注释"  
> 覆盖上次的提交：git commit --amend -m "注释"
4. show
> git show xxx  // 显示commit xxx 的修改
5. reset
<pre>
git包含3个状态：HEAD, INDEX, WORKING
git add:	将WORKING的改变加到INDEX, WORKING=INDEX!=HEAD
git commit:	将INDEX的状态加到HEAD, WORKING=INDEX=HEAD
与此相反：
git reset --soft xxx            // 将HEAD改到xxx, HEAD!=INDEX=WORKING, 相当于commit之前的状态
git reset --mixed(default) xxx  // 将HEAD和INDEX都改到xxx, HEAD=INDEX!=WORKING的还在, 
                                // 相当于add之前的状态 
git reset --hard xxx            // 将HEAD和INDEX和WORKING都改到xxx, 本地修改WORKING丢失
</pre>

分支命令
==========
1. 查看本地分支
> git branch
2. 查看远程分支
> git branch -r
3. 查看本地和远程分支
> git brach -a
4. 创建本地分支
> git branch [branch-name]
5. 切换分支
> git checkout [branch-name]
6. 创建新分支并立即切换到新分支
> git checkout -b [name]
7. 删除分支
> git branch -D [name]
8. 合并分支
> git merge [name] //将名称为[name]的分支与当前分支合并  


命令汇总
============

![/res/images/git/git-command.png]({{'/res/images/git/git-command.png' | prepend: site.baseurl }})  


工作区、暂存区和版本库
========================


1. 工作区：就是你在电脑里能看到的目录和文件。  
2. 暂存区：英文叫stage, 或index。一般存放在 ".git目录下" 下的index文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。  
3. 版本库：工作区有一个隐藏目录.git，这个不算工作区，而是Git的版本库。  
下面这个图展示了工作区、版本库中的暂存区和版本库之间的关系：  

![/res/images/git/git-struct.png]({{'/res/images/git/git-struct.png' | prepend: site.baseurl }})

图中左侧为工作区，右侧为版本库。在版本库中标记为 "index" 的区域是暂存区（stage, index），标记为 "master" 的是 master 分支所代表的目录树。  

图中我们可以看出此时 "HEAD" 实际是指向 master 分支的一个"游标"。所以图示的命令中出现 HEAD 的地方可以用 master 来替换。  

图中的 objects 标识的区域为 Git 的对象库，实际位于 ".git/objects" 目录下，里面包含了创建的各种对象及内容。  

当对工作区修改（或新增）的文件执行 "git add" 命令时，暂存区的目录树被更新，同时工作区修改（或新增）的文件内容被写入到对象库中的一个新的对象中，而该对象的ID被记录在暂存区的文件索引中。  

当执行提交操作（git commit）时，暂存区的目录树写到版本库（对象库）中，master 分支会做相应的更新。即 master 指向的目录树就是提交时暂存区的目录树。  

当执行 "git reset HEAD" 命令时，暂存区的目录树会被重写，被 master 分支指向的目录树所替换，但是工作区不受影响。  

当执行 "git rm --cached <file>" 命令时，会直接从暂存区删除文件，工作区则不做出改变。  

当执行 "git checkout ." 或者 "git checkout -- <file>" 命令时，会用暂存区全部或指定的文件替换工作区的文件。这个操作很危险，会清除工作区中未添加到暂存区的改动。  

当执行 "git checkout HEAD ." 或者 "git checkout HEAD <file>" 命令时，会用 HEAD 指向的 master 分支中的全部或者部分文件替换暂存区和以及工作区中的文件。这个命令也是极具危险性的，因为不但会清除工作区中未提交的改动，也会清除暂存区中未提交的改动。  

windows git 安装
=================

下载地址 [https://git-scm.com/downloads](https://git-scm.com/downloads) 或  [https://gitforwindows.org/](https://gitforwindows.org/)