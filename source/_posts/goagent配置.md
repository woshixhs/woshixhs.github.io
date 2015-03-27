title: "goagent配置"
date: 2015-03-27 20:35:10
categories: 网络工具
tags: goagent

----------

#####**goagent配置**
配置[goagent](https://github.com/goagent/goagent)比较简单,直接参考文档就行了.

[Simple Guide](https://github.com/goagent/goagent/blob/wiki/SimpleGuide.md)
[Graphic Guide](https://github.com/goagent/goagent/blob/wiki/InstallGuide.md)

#####**FAQ**

 - 上传过程中,遇到google帐号密码错误,估计是使用16位应用专用密码的原因.这个时候,可以参考Graphic Guide中的地址,生成一个应用密码,如果你没有启用二次验证,先启用二次验证,之后,任何选择一个生成一个密码就可以.
 - 登录google,会出现不安全的链接.解决方案
 
		FireFox->选项->高级->加密->查看证书->证书机构->导入证书, 选择   local\ca.crt, 勾选所有项，导入
		Chrome->设置->管理证书->授权中心->导入
