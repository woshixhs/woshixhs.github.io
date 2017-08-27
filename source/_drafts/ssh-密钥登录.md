title: ssh 密钥登录
date: 2017-08-27 12:44:36
categories: linux
tags: sshd
---

#### 生成密钥 ####
```
ssh-keygen -t rsa
```
生成密钥对，可以不输入密码

#### 把公钥传到远程服务器 ####
```
ssh-copy-id -i ~/.ssh/id_xxx.pub -p port username@server
```
如果文件名字默认是id_rsa.pub 可以不用输入-i,如果port是22，不需要-p,如果本地用户名跟远程是一直的，username也可以不用.ssh-copy-id默认会把当前的key追加到远程机器的authorized_keys的末尾。

#### 管理多组密钥对 #####
类似配置git一样，这里也可以配置多对密钥对, 同样适用~/.ssh/config 来管理。每1个ssh服务器对于一对密钥对，或者可以对所有的ssh服务器，适用同1对。配置文件
```
~/.ssh/config
Host server1
IdentitiesOnly yes
IdentityFile ~/.ssh/id_rsa_SERVER1
  # CheckHostIP yes
  # Port 22
Host server2
IdentitiesOnly yes
IdentityFile ~/.ssh/id_rsa_SERVER2
  # CheckHostIP yes
  # Port 22
ControlMaster auto
ControlPath /tmp/%r@%h:%p
```
#### 安全性 ####
当配置完成可以使用key登录之后，可以禁用password登录，并且禁用root登录
```
/etc/ssh/sshd_config
RSAAuthentication yes
PubkeyAuthentication yes
PermitRootLogin yes
PasswordAuthentication no
#ChallengeResponseAuthentication no
```
设置完成之后，重启sshd 服务




### 参考资料 ###
[使用SSH密钥登录让Linux VPS服务器更安全](https://www.iwwenbo.com/linux-ssh-authorized-keys-login/)

[设置 SSH 通过密钥登录](https://hyjk2000.github.io/2012/03/16/how-to-set-up-ssh-keys/)

[SSH keys (简体中文)](https://wiki.archlinux.org/index.php/SSH_keys_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87))

