title: webpack资料
categories: web前端
tags: webpack
date: 2016-12-12 17:01:14

---


#webpack资料


* [webpack](https://github.com/webpack/webpack)

* [webpack.github.io](https://webpack.github.io/)

* [webpack 官方doc](http://webpack.github.io/docs/)

* [webpack-handbook](http://zhaoda.net/webpack-handbook/module-system.html)
	 
	 使用简单例子，介绍了webpack的使用
	 
	 问题：
	 
	 *  1: Mac 平台安装webpack(本地安装), webpack命令不能执行，需要设置PATH
	 	
	 	
	 	使用shell的临时环境变量，（./node-module/.bin/）
	 	
	 	
	 	```
	 	export PATH=$PATH:(path)
	 	```

	* 2: 在npm中使用Webpack
		
		我们在package.json中设置一个快捷方式，运行webpack。

		```package.json 文件
		...
		"scripts": {
   		 "build": "webpack"
  		}
		... 
		``` 
		现在我们直接运行`npm run build`命令实现与上面相同的功能。
		[参考](https://segmentfault.com/a/1190000007806707)


* [webpack-guide](https://webpack.toobug.net/zh-cn/)

	更加详细介绍了webpack的使用，比webpack-handbook要详细，是webpack-handbook的深入指南

