title: "git 常用命令"
date: 2015-03-31 21:12:57
categories: git
tags:

----------
#####**创建git**
	git init
#####**添加远程仓库**
	git remote add origin git@server-name:path/repo-name.git  #添加一个远程库, 这样就把本地跟远程的git url地址绑定了
#####**查看远程仓库**
	git remote
	git remove -v
#####**添加本地文件到stash** 
	git add file
#####**本地提交到仓库**
	git commit
#####**推送分支到远程**
	git push, 
	git push origin master,一般默认推送到master分支
#####**获取远程分支**
	git clone,  获取远程分支的代码
	git pull, 获取当前分支的最新代码
	git pull = git fetch + merge to local
	git checkout , 切换分支
	git checkout -b dev origin/dev, #创建远程origin的dev分支到本地，并命名为dev
	git branch --set-upstream branch-name origin/branch-name，可以建立起本地分支和远程分支的关联，之后可以直接git pull从远程抓取分支。
#####**删除远程分支**
	git push origin --delete bugfix
#####删除本地分支
	git branch -d xxx, 
#####**查看分支命令**
	git branch  本地
	git branch -r 远程
	git branch -a 所有


----------


参考:

 - http://wuchong.me/blog/2015/03/30/git-useful-skills/#more
 - http://robbinfan.com/blog/34/git-common-command
 - [git - 简明指南](http://rogerdudler.github.io/git-guide/index.zh.html)
 - [Git 常用命令速查表](https://gitcafe.com/GitCafe/Help/wiki/Git-%E5%B8%B8%E7%94%A8%E5%91%BD%E4%BB%A4%E9%80%9F%E6%9F%A5%E8%A1%A8)

	
	
