title: "npm 使用"
date: 2015-04-16 23:07:34
categories: npm
tags:

----------
#####**npm 常用命令**
	npm install <package name> -g
	npm uninstall <package name>
	npm search <package name>
	npm ls -g
	npm update -g
   [参考](http://dreamerslab.com/blog/tw/npm-basic-commands/)

#####**npm 更新**
	npm -g update
	如果更新的版本有问题,可以使用预览版本
    npm i -g npm@next 预览版本,
   [参考](http://segmentfault.com/q/1010000002437961)

#####**npm 添加镜像**
使用npm下载比较慢,可以使用如下的命令添加镜像

 - 通过config命令
	
		npm config set registry https://registry.npm.taobao.org 
		npm info underscore （如果上面配置正确这个命令会有字符串response）
 - 命令行指定
 
		 npm --registry https://registry.npm.taobao.org info underscore 
 - 编辑 ~/.npmrc 加入下面内容
			  
		 registry = https://registry.npm.taobao.org
   [参考](https://cnodejs.org/topic/4f9904f9407edba21468f31e)

#####**node runtime 更新**
	npm install -g n
	n stable
   [参考](http://www.jb51.net/article/52409.htm)

	

