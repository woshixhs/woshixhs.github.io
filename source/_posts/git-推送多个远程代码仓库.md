title: git 推送多个远程代码仓库
categories: git
tags: git
date: 2016-04-02 23:32:42
---


####场景

很多时候，我们需要1份本地的代码，保存到多份代码仓库，对应这种情况，git中还是很容易处理的

#####命令git remote

	$ git remote
这个命令，可以查看当前的远程仓库。如果有多个，会列出来。


#####添加远程仓库

	$ git remote add [shortname] [url]
	$ git remote add coding git@git.coding.net:woshixhs/woshixhs.git
这样就添加了一个新的远程代码仓库

#####删除远程仓库

	$ git remote rm 
	$ git remote rm  coding
	
#####推送数据到远程仓库

	$ git push <远程主机名> <本地分支名>:<远程分支名>


