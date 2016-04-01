
title: "Gitub Hexo 建立博客"
date: 2015-03-17 21:04:10
categories: 搭建博客
tags:

---


> 使用Github hexo建立博客

#####软件安装

	安装git, node.js, 注册github. 这个比较简单,这里不做记录,
	特别说明,
	对于开发者来说,node.js的版本比较多,
	可以使用Node Version Manager(NVM)来安装.

#####github

	你可以有2个选择, 可以选择用户,组织,或是项目的website的Pages,
	一般选择用户, 例如: username.github.io, 这里的username就是你的github账号名字.
	注意名字不要弄错,名字不能填错.

#####hexo

	接下来就是hexo的使用了.开始需要使用hexo init建立目录.
	之后可以使用hexo new 建立一个文档, 使用[MarkDown](https://stackedit.io/editor)编辑工具编辑文章,
	使用hexo server, 启动服务,在浏览器查看效果.最后没有问题之后,使用hexo deploy做部署,
	上传到github的master账号(这里选择了用户site).deploy 
	可以在config文件下面配置,账号信息,哪个分支都可以配置.最好使用hexo-deployer-git插件部署.部署完成,
	你生成的html,就会部署到master分支.

#####备份博客环境

	之前的步骤,可以使用你的环境上传你的博客文章,不过你切换了环境之后,就没办法写文章了,
	所以,这里需要备份一个环境,环境备份好之后,到了新的电脑,
	你只需要把软件安装成功,通过git 把环境下载下来,就可以直接写文章.
	通过命令git branch source建立source分支,
	之后切换到分支git checkout source切换到分析.
	删除本地的文件,把之前写文章的环境拷贝到这个环境下
	(之前由于安装主题,可能有.git的隐藏目录,需要手工删除,否则主题会出现不能备份的情况.) 
	使用把这个环境上传到分支(git push).
	下载环境, git clone,只能下载master分支的代码,
	首先我们git clone代码. 之后使用git branch -a,
	获取分支列表: 
	remotes/origin/HEAD -> origin/master
	remotes/origin/master
	remotes/origin/source 
	之后使用git checkout -b  source origin/source, 
	下载远程分支source,并且本地切换到分支source.


