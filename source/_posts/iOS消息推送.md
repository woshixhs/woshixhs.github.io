title: "iOS消息推送"
date: 2015-03-21 21:43:36
categories: iOS
tags: iOS推送

---

> iOS 推送原理

这个可以参考这个[AVOS Cloud](https://blog.leancloud.cn/1163/)文章

#####iOS 证书制作
	证书分为开发证书, Adhoc证书, 发布版证书.

#####iOS 推送证书过期处理
	证书过一年会过期,需要重新revoke生成,最好csr文件是同一个.

#####iOS推送测试
	可以使用Mac 上的PushMeBaby做测试，不过目前测试失败，估计API升级导致的原因。
可以参考如下的文章
	 Php的测试方案也失效了，具体没去了解原因(估计是证书制作的方法换了)。

 - http://www.cnblogs.com/gpwzw/archive/2012/03/31/apple_push_notification_services_tutorial_part_1-2.html
 - http://www.raywenderlich.com/32960/apple-push-notification-services-in-ios-6-tutorial-part-1
 
有效的php证书制作方法:

#####Java推送
Java推送用的比较多的开源lib,[java-apns](https://github.com/notnoop/java-apns), 还有JavaPNS,2个lib的比较:

 -  **JavaPNS** 
		 优点是简单，但缺点也很明显，效率不高，没有考虑各种通知发送出错的情况。这个库适合那些每天通知发送量特别小，并且用户收没收到也无所谓的应用
 - **java-apns**
      notnoop的Java APNS就要强大很多，目前它应该是使用最多的Java类库。随着使用的加深，发现它有很多不完善之处。最严重的问题是，运行一段时间后就死掉了，通知再也发不出去了，但重启下就又恢复了。经查，应该是死锁了，通知堆积在内存中并没有真正发出去。这对于对消息送达率和及时性要求非常高的聊天软件来说，是不能忍受的。
      
       可以使用java-apns的项目,用来测试iOS 的推送, 比较方便.


----------

目前,暂时没有分析其他java lib, 目前有[dbay-apns-for-java](https://github.com/RamosLi/dbay-apns-for-java) .[pushy](https://github.com/relayrides/pushy), 后续需要测试分析,性能,
主要是对长链接的处理.(未完待续)


