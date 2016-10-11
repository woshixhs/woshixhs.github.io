title: "linux android device 调试"
date: 2015-04-17 22:36:32
categories: Android
tags: Android USB

----------

#####**Android Device调试**

 - windows
	 需要安装驱动
 - Mac
    不需要安装任何驱动
 - linux
   以 root 权限在 /etc/udev/rules.d/ 的目录下创建 .rules 配置文件
   sudo touch 51-android.rules 
  SUBSYSTEM=="usb", ATTR{idVendor}=="0bb4", MODE="0666",   GROUP="plugdev" 
  之后执行命令chmod a+r /etc/udev/rules.d/51-android.rules
  执行完成之后,重新启动就可以了
  命令
  sudo /etc/init.d/udev restart 
  adb kill-server
  adb devices

#####**idVendor**
在安卓开发文档中有个列表,有个Vendor list.对于单台设备,也可以使用命令lsusb查看, 通过插上手机,跟没有插上手机,可以看到手机的idVendor


#####**参考文档**  
http://my.oschina.net/u/260921/blog/469626
http://www.oschina.net/question/4873_27142
http://wujianjun.iteye.com/blog/1748423
https://developer.android.com/tools/device.html

