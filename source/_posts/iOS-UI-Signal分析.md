title: "iOS UI Signal分析"
date: 2015-04-10 18:01:26
categories: iOS 
tags: UI Signal

----------
#####**UI Signal**
	事件响应，传递，是整个UI系统的关键。这里使用了Bee UI Signal, 重新定义了UI的事件传递，也了解下UI中的重要的响应链。
	

 - view的物理布局
		  UIViewController中，里面有一个View1，之后View1里面有个View2，

 - 事件的传递
	  View2可以接受点击事件，View1也可以接受点击事件。当点击View2的时候，整个消息链路是怎么样的？
	  整个消息链路是透传的，就是转发接受到的消息，那整个消息链路是View2->View1>UIViewController,
	  消息是这样传递的，处理结果刚好相反，递归调用。这里，你也可以不传递消息，例如链路可以是View2，或是View2->View1

 - 场景使用
	等具体应用的时候，每个View的容器，就可以添加自己感兴趣的事件，进行响应，其他就不用关心了。
  
#####**Demo**
 [ios-ui-signal](https://github.com/gelosie/ios-ui-signal)