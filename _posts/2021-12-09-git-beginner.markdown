---
layout: post
title:  "项目中Git的使用简单流程"
date:   2021-12-09 23:57:01 +0800
categories: git begin
---

我日常是 TortoiseGit 和 bash 都有用的
下面是一些 bash 的操作
最开始：
* git clone 远端网址 本地目录名<br>
    ```
    git clone http://aaa.bbb.ccc zwjWork
    ```
* 进入到刚才拉取的目录 cd
    ```
	cd zwjWork
    ```
* 查看全部分支 
    ```
    git branch -a
    ```
* 使用工作分支创建本地分支，并切换过去
    ```
	git checkout -b develop origin/develop
    ```
	这样就建立起了本地的远端工作分支，以后的工作，都是基于这个分支进行
* 创建本地工作分支，用于各种工作
    ```
	git checkout -b local_dev develop
    ```
	这一步，以后可能会有各种创建本地的分支，用来做某个时间点不同的事情
	会有 local_dev2/3/4 等等各种名字的某个功能的开发分支

工作中：
* 在 local_dev 上各种工作，但最好时不时同步一下develop
* 把修改的东西存到栈种
    ```
	git stash
    ```
* 切换到本地存储的远端开发目录
	```
    git checkout develop
    ```
* 拉取远端的数据到本地 develop 分支
	```
    git pull origin develop
    ```
* 回到各个本地功能开发目录中
	```
    git check local_dev
    ```
* 把刚才拉取的，嫁接到功能开发目录，这里可能会出现冲突，需要解决好
    ```
	git rebase develop 
    ```
* 把之前存储在栈中，弹出来，这里也可能会有冲突，需要解决好
	```
    git stash pop
    ```
	注意：如果有冲突，栈中还会保留着stash的内容，酌情考虑是否清掉

提交：
* 上面的 stash、checkout、pull、rebase 操作后
* 把我自己的开发分支push 到我自己远端仓库的 develop 分支
	```
    git push 我自己的远端仓库 local_dev:develop
    ```
* 切换到网页端，申请合并到主分支，之后就有代码审查员进行审查，之后合并或者打