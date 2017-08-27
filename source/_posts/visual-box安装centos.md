title: visual box安装centos
categories: linux
date: 2017-07-30 00:07:51
tags:
---


## visual box 安装 centos
* visual box 开始设置

    对于生产机,选择mininal安装，选择英文语言。分区的选择,
    设置swap分区等
* 添加用户

    最好不要使用root进行登录，而是需要新建1个用户来登录
    ```
    useradd  添加1个新用户
    passwd 为新用户设置密码
    ```
* 给一般用户sudo权限

    ```
    visudo
    使用这个命令，给生成的账号添加权限
    ```
* 配置网络环境

    ```
    sudo yum install net-tools
    centos7选择minal安装之后，一些基础的网络没有，所以先按照一些工具
    ```

* 设置网卡网络环境参数
    * 设置IP地址

        说明：CentOS 7.x默认安装好之后是没有自动开启网络连接的！

        cd  /etc/sysconfig/network-scripts/  #进入网络配置文件目录

        vi  ifcfg-ens33  #编辑配置文件，添加修改以下内容

        BOOTPROTO=static  #启用静态IP地址

        ONBOOT=yes  #开启自动启用网络连接

        IPADDR0=192.168.21.130  #设置IP地址

        PREFIXO0=24  #设置子网掩码

        GATEWAY0=192.168.21.2  #设置网关

        DNS1=8.8.8.8  #设置主DNS

        DNS2=8.8.4.4  #设置备DNS

        :wq!  #保存退出

    * 把网卡名称ifcfg-ens33改为ifcfg-eth0

        CentOS 7.x系统中网卡命名规则被重新定义，可能会是”ifcfg-ens33”等，下面我们把网卡改为ifcfg-eth0这种。

        1. cd  /etc/sysconfig/network-scripts/

            mv  ifcfg-ens33  ifcfg-eth0  #修改名称

            vi  ifcfg-eth0  #编辑

            NAME=eth0   #修改

            DEVICE=eth0   #修改

            :wq! #保存退出

        2. vi /etc/sysconfig/grub  #编辑

            在”GRUB_CMDLINE_LINUX“变量中添加一句”net.ifnames=0 biosdevname=0“

            :wq! #保存退出

        3. 运行命令：grub2-mkconfig -o /boot/grub2/grub.cfg  #重新生成grub配置并更新内核参数

        4. 添加udev的规则

            在”/etc/udev/rules.d“目录中创建一个网卡规则”70-persistent-net.rules“,并写入下面的语句:

            cd  /etc/udev/rules.d
            vi  70-persistent-net.rules   #添加

            SUBSYSTEM=="net",ACTION=="add",DRIVERS=="?*",ATTR{address}=="00:0c:29:1e:a3:77",ATTR｛type｝=="1" ,KERNEL=="eth*",NAME="eth0"

            :wq! #保存退出

        5. shutdown -r now  #重启系统

            网卡已经更改为eth0

* 设置visual box的网络

    1. 网卡1配置为NAT

    2. 网卡2配置为host-only


* 可以使用ssh登录虚拟机
    宿主机修改host 配置虚假机域名, 并且配置为密钥登录

* 共享文件夹
    
    1. 电脑下载VBoxAdditions, http://download.virtualbox.org/virtualbox/5.1.26/VBoxGuestAdditions_5.1.26.iso, 可以在http://download.virtualbox.org/virtualbox/查找

    2.  CentOS挂上光驱：
    ```
    mount /dev/cdrom /mnt/
    ```

    3. 将光驱内的文件夹复制到硬盘中。（如果直接在光驱中执行安装，会因为权限问题导致无法安装。）
    ```
    cp -R /mnt/ /usr/local/src/VBoxAdditions

    ```

    4. 可选）安装前需要设置安装环境，如果已设置，那么这一步可以跳过：
    ```
    yum install -y make gcc gcc-c++ kernel kernel-devel
    ```

    5. 进入文件夹，开始安装：./VBoxLinuxAdditions.run

    6. 启用共享文件夹：
    ```
    mount -t vboxsf 共享文件夹 本地文件夹
    ```
    如何visual box设置了自动挂载，那么可以查看df

    

## 参考资料
* [CentOS 7.3.1611系统安装配置图解教程
](http://www.osyunwei.com/archives/10003.html)
* [CentOS 7 安装教程、硬盘分区、LVM、网络配置、软件源配置、制作
](http://www.chengxuyuans.com/Unix/83454.html)
* [VirtualBox 虚拟机的网络设置
](https://cnzhx.net/blog/virtualbox-vm-network-setting/)
* [如何配置 VirtualBox 中的客户机与宿主机之间的网络连接](https://linux.cn/article-8252-1.html)
* [virtualbox 常用网络模式解释和配置](http://cizixs.com/2017/03/09/virtualbox-network-mode-explained)
* [Mac系统VirtualBox中CentOS启用共享文件夹](http://blog.csdn.net/suma110/article/details/54343686)
* [在VirtualBox中与主机共享文件夹](http://www.linuxidc.com/Linux/2016-08/134292.htm)
