title: "git account配置"
date: 2015-03-24 21:26:04
categories: git
tags:  github配置

----------
#####git的配置
 1. **安装git**
 2. **生成本地SSH密匙(这是关键的一步)**
	 如果用户是第一次使用git，就需要现在家目录创建一个.ssh文件夹，生成密匙用的默认文件夹，由于是隐藏的，用户可以在家目录按Ctrl+h来显示隐藏文件夹，看看是否已经有这个.ssh文件夹，如果没有，就打开终端输入如下命令：
	 
> 	mkdir ~/.ssh

PS:要是没有创建之前已经有的.ssh目录的话，切换到.ssh，用ls命令查看目录下是否有id_rsa.pub与id_rsa两个文件，有的话就代表密匙已经生成过，就不需要再执行生产密匙的步骤。
创建好目录之后，就开始输入如下命令生成密匙。

> ssh-keygen -t rsa -C "your_email@example.com"

        注意，为了保证是默认设置，当提示让输入保存密匙的文件的时候，直接按回车键就可以了。之后会让输入密码，和确认密码，可以输要保证两次一样，也可以都按回车键不输密码。执行结束之后终端会输出如下信息。

> Your identification has been saved in /home/you/.ssh/id_rsa. Your
> public key has been saved in /home/you/.ssh/id_rsa.pub. The key
> fingerprint is:  01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db
> your_email@example.com


 3. **添加密匙到github上**
	 上一步会在/~/home/.ssh/文件夹中生成id_rsa.pub与id_rsa两个文件.其中id_rsa是私钥,保存存在本地,id_rsa.pub是公钥.然后将公钥中的内容粘贴到你github帐号中的SSH Public Keys的位置。注意小心不要复制到空格。
不过还有另一种方法将key复制到粘贴板：

> sudo apt-get install xclip 
> xclip -sel clip < ~/.ssh/id_rsa.pub

执行这两个命令之后，就复制id_rsa.pub的内容到粘贴版了。
        打开github网站，点击右上角Account settings图标，然后在左边栏选择SSH Keys，接着点击右边的Add SSH Key，title可以随便填，key里面直接右键粘贴就可以了。然后点击添加，如果提示添加失败，可能就是复制的时候有问题，所以推荐使用上面的命令来复制，而不是打开本地key文件去复制。
 4. **测试是否成功**

> 	 ssh -T git@github.com

 为了确保一切OK，我们测试是否添加key成功，其间如果用户在第一步设置了密码，会提示输入密码。请确保不要更改git@github.com。输入上面的命令之后，你会看到一个警告，不用管，输入yes就行。过一会就会出现如下信息。

> Hi yourname You've successfully authenticated, but GitHub does not
> provide shell access.
 
 如果yourname显示的正确，就代表你已经成功安装了SHH Key了。
 5 **初始化git配置**
> 	git config --global user.name "username"
> 	git config --global user.email username@xxx.com

 6 **补充：避免每次提交都输入用户名和密码**
        如果不想每次都输入用户名和密码的话，可以使用ssh方式，ssh方式是通过密匙认证的不需要输入密码，https方式每次都需要输入用户名和密码，如果想改为ssh方式，只需要找到项目目录下的.git文件夹，然后进入到该文件夹里面找到config文件，编辑该文件将其中的URL改为ssh提交的方式改过之后是这样的:
>  [remote "origin"]
>  url = git@github.com:username/work.git
> fetch = +refs/heads/*:refs/remotes/origin/*

7 参考文章
http://www.picksomething.cn/?p=28
https://help.github.com/articles/generating-ssh-keys/

----------




