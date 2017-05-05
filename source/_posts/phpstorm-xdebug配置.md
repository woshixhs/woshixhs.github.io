title: phpstorm xdebug配置
categories: php
tags: xdebug
date: 2017-05-05 12:33:07
---


#### 准备工作
* xdebug的安装

  配置文件
  ```
  [xdebug]
  xdebug.remote_enable=1
  xdebug.remote_host=127.0.0.1
  xdebug.remote_port=9001
  xdebug.profiler_enable=1
  xdebug.idekey=PHPSTORM
  ```
* phpstorm 设置

  ```
  php debug 端口设置为9001
  php dbgp proxy 设置，端口也保存一致
  配置一个server
  ```
* chrome 浏览器xdebug 配置


####参考资料

[PHP调试利器XDebug Mac下在phpstorm中的安装与使用](https://www.funboxpower.com/mac_php_xdebug_phpstorm_install)
