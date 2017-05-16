title: "git 常用命令"
date: 2015-03-31 21:12:57
categories: git
tags:

----------
#####**创建git**
	```
	git init
	```
#####**添加远程仓库**
	```
	git remote add [shortname] [url]
	git remote add origin git@server-name:path/repo-name.git
	```
	添加一个远程库, 这样就把本地跟远程的git url地址绑定了
	通过这个方法,可以对同一个仓库,添加多个远程仓库
#####**删除远程仓库**
	```
	$ git remote rm
	$ git remote rm  coding
	```
#####**查看远程仓库**
  ```
	git remote
	git remove -v
	```
#####**添加本地文件到stash**
	```
	git add file
	```
#####**本地提交到仓库**
	```
	git commit
	```
#####**推送分支到远程**
	```
	git push <远程主机名> <本地分支名>:<远程分支名>
	git push,
	后续参数都省略,或是已经本地跟远程已经建立关联
	git push origin master,
	一般默认推送到master分支, 本地分支跟远程分支同名
	```
#####**获取远程分支**
	```
	git clone,  获取远程分支的代码
	git pull, 获取当前分支的最新代码
	git pull = git fetch + merge to local
	git fetch origin
	git merge origin/next
	git pull <远程主机名> <远程分支名>:<本地分支名>
  ```

#####**clone tag仓库**
	```
	git checkout -b branch_name tag_name

	```
	这样会从 tag 创建一个分支，然后就和普通的 git 操作一样了。
	否则如果你做了修改，git 可能会提示你当前处于一个“detached HEAD" 状态
#####**切换远程**
	```
	git checkout , 切换分支
	git checkout -b dev origin/dev,
	#创建远程origin的dev分支到本地，并命名为dev
	git branch --set-upstream branch-name origin/branch-name，
	可以建立起本地分支和远程分支的关联，之后可以直接git pull从远程抓取分支。
	```

#####**合并远程**
	```
	git merge <branch>
	```

用于合并指定分支到当前分支,
是Fast-forward合并分支，这种模式下，删除分支后，会丢掉分支信息。
	```
	git merge --no-ff -m "..." <branch>
	```

--no-ff参数，表示禁用Fast forward
本次合并要创建一个新的commit，所以加上-m参数，把commit描述写进去

#####**删除远程分支**
	```
	git push <远程主机名> --delete <远程分知名>
	git push origin --delete bugfix
	```
#####**删除本地分支**
	```
	git branch -d xxx,
	```
#####**查看分支命令**
	```
	git branch  本地
	git branch -r 远程
	git branch -a 所有
	```
#####**撤销修改**
修改了内容,不过没有通过git add file，添加到stash

单个文件

	git checkout -- file
	discard file, file修改内容被放弃

所有文件

	git checkout -- .
	当前目录的所有问题放弃


如果这个时候，已经通过git add 添加到stash，还没有push

	git reset HEAD <file>...
	把暂存区的修改撤销掉（unstage），重新放回工作区：


添加到文件，还没有被tracked

	git clean -fdx
	把没有tracked的文件放弃


#####**回撤版本**



#####**创建标签**

	git tag <name>

默认标签是打在最新提交的commit上的，可以打在一个commit id上面，

	git tag <name> commit id
这样就算当时没打标签，也可以补打标签

创建带说明的标签
  ```
	git tag -a <tagname> -m "..."
	-a 标签名字
  －m 说明性文字
	```

#####**查看所有标签**
	```
	git tag
	```
#####**查看标签信息**
	```
	git show <tagname>
	```

#####**删除标签**

		git tag  －d <tagname>
删除本地标签

如果要删除远程标签,必须先删除本地标签，之后删除远程标签

	git push origin :refs/tags/<tagname>

#####**推送标签**

	git push origin <tagname>
推送单个标签

	git push origin --tags
一次性推送全部尚未推送到远程的本地标签




 - 还没add到stash
 - 已经commit到stash
 - 已经push

#####**.gitignore**
	```
	# 此为注释 – 将被 Git 忽略
	*.a       # 忽略所有 .a 结尾的文件
	!lib.a    # 但 lib.a 除外
	/TODO     # 仅仅忽略项目根目录下的 TODO 文件，不包括 subdir/TODO
	build/    # 忽略 build/ 目录下的所有文件
	doc/*.txt # 会忽略 doc/notes.txt 但不包括 doc/server/arch.txt
	```
	这个规则比较简单，如果我们要忽律那些已经添加到仓库的代码，那么，需要先把本地缓存删除(改变成未track状态)，之后再添加

	```
	git rm -r --cached .
	```
----------


参考:

 - http://wuchong.me/blog/2015/03/30/git-useful-skills/#more
 - http://robbinfan.com/blog/34/git-common-command
 - [廖雪峰的Git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
 - [git - 简明指南](http://rogerdudler.github.io/git-guide/index.zh.html)
 - [Git 常用命令速查表](https://gitcafe.com/GitCafe/Help/wiki/Git-%E5%B8%B8%E7%94%A8%E5%91%BD%E4%BB%A4%E9%80%9F%E6%9F%A5%E8%A1%A8)
