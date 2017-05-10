title: Mac 常用命令
date: 2017-05-05 22:23:56
categories: Mac command line
tags: Mac

---

#### 硬链接跟软链接
  * 硬链接
    相当于引用计数+1, 需要把所有文件删除了，文件才可以删除
    ```
    格式：ln [原文件] [硬链接文件]
    ```
  * 软链接
    就是文件的快捷方式
    ```
    格式：ln -s [原文件] [软链接文件]
    ```

  [参考文档](https://slarker.me/mac-file-link/)
