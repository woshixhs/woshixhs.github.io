title: Laravel入门知识
categories: php
tags: Laravel
date: 2017-05-05 09:40:32
---


#### 入门示例code

* [A sample task list application with authentication](https://github.com/laravel/quickstart-intermediate)
* [A sample task list application](https://github.com/laravel/quickstart-basic)
* [Laravel 5 系列入门教程](https://github.com/johnlui/Learn-Laravel-5)

#### 入门知识点文档

[Laravel 5.1 基础教程](http://laravelacademy.org/laravel-tutorial-5_1)

[Laravel 文档英文](https://laravel.com/docs/5.4)

[Laravel 文档中文](https://docs.golaravel.com/docs/5.4/installation/)


#### 帮助信息

[laravel-ide-helper](https://github.com/barryvdh/laravel-ide-helper)

[laravel-debugbar](https://github.com/barryvdh/laravel-debugbar)参考链接http://laravelacademy.org/post/2774.html

[laravel-modules](https://nwidart.com/laravel-modules/)


#### 添加模块后使用事项
* 添加laravel-modules

  添加完成之后，需要修改项目根目录下的composer.json文件，添加autoloading PSR-4:
  ```
  /file: composer.json
  "psr-4": {
  "App": "app/",
  "Modules": "modules/"
  }
  ```
之后需要运行命令 `compser dump-autoload`
