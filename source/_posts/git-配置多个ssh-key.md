title: git 配置多个ssh key
categories: git
tags: ssh key
date: 2016-04-02 23:10:49
---



> 先配置1个ssh key


#####生成ssh key同时保存文件名

使用ssh-keygen 生成，最后阶段，选择1个名字保存

#####上次key到website


#####添加私钥

	$ ssh-add ~/.ssh/id_rsa
	
如果执行ssh-add时提示"Could not open a connection to your authentication agent"，可以现执行命令：

	$ ssh-agent bash

然后再运行ssh-add命令。

	# 可以通过 ssh-add -l 来确私钥列表
	$ ssh-add -l
	# 可以通过 ssh-add -D 来清空私钥列表
	$ ssh-add -D


#####新增并配置config文件

如果config不存在，先添加；存在则自己修改
	
	touch ~/.ssh/config
	
在config 文件里添加如下内容

	#bitbucket
	Host bitbucket.org
    HostName bitbucket.org
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/id_rsa_bitbucket

