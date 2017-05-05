title: Mac php开发环境 安装
categories: php
tags: php
date: 2016-04-18 15:42:56
---



#### php

按照之前查看有哪些选项，可以使用命令
``
  brew info php71
``

安装命令
``
brew install php71 \
--with-debug \
--with-homebrew-curl \
--with-homebrew-libxslt \
--with-imap \
``

#### 安装php xdebug
  ``
  brew install php71-xdebug --build-from-source
  ``

#### mysql

安装命令
``
brew install mysql
``

#### nginx
安装命令
``
brew install nginx
``

#### 参考资料
https://segmentfault.com/a/1190000002963355

http://avnpc.com/pages/install-lnmp-on-osx

http://yansu.org/2013/12/11/lamp-in-mac.html

http://my.oschina.net/sunxichao/blog/366282

http://blog.devtang.com/2014/02/26/the-introduction-of-homebrew-and-brewcask/

http://avnpc.com/pages/install-lnmp-on-osx

http://jigsawye.com/2016/02/01/setup-laravel-development-environment-with-homebrew/
