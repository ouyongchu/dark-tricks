# 如何判断一个链接是否安全 —— 神器whois

> 本文源于真实案例，若有疏漏之处，欢迎各位拍砖。

---
### 本文目标
给定一条未知的链接， 如何判断是否存在陷阱or欺诈？

### 本文局限
这里不讨论域名劫持、流量拦截，这里仅讨论给定一个陌生的链接，可信度有多高。
---
### 一个案例
2015年12月20日，师妹收到一条短信，内容如下：(聪明的你，看到如此具体的时间，应该知道是条线索)
![](https://github.com/ouyongchu/dark-tricks/blob/master/images/message.JPG)

发送短信的号码是95555，是否可信？

以下就两个层面分析：
#### 心理层面
1. 95555短信号码，确实是招行银行的，但也有可能是伪基站发送的。（前不久某室友就被"某苹果官方号码"套出各种私人信息，丢失的iphone估计也被解锁了-。-）
2. 短信通知过于紧急。"预期银行卡作废处理"，中国银行卡账户上无存款且3年未使用，才会自动销卡，你随便发条短信就说银行卡作废处理，连个电话都不给？

#### 技术层面
既然是招商银行发来的，若要登录，唯一可信的只有官网。招行官网 www.cmbchina.com 跟 wap.cmblkg.com看起来都有"cmb", 实则二级域名不同。

这时候亮出我们的神器whois, 这里我用http://whois.chinaz.com/.二级域名cmblkg.com信息如下：

![](https://raw.githubusercontent.com/ouyongchu/dark-tricks/master/images/cmblkg.com.png)

WTF!! 域名创建时间是2015年12月20日，不就是师妹收到短信的这天？真相只有一个：麻蛋这个域名是今天注册，准备用来坑蒙拐骗的！

看看人家官网域名cmbchina.com信息, 97年创建（假如一个骗子97年注册个域名然后今天才来骗你，那我也没辙了=。=）：

![](https://raw.githubusercontent.com/ouyongchu/dark-tricks/master/images/cmbchina.com.jpg)


另外，使用mac和linux的童鞋，可以在终端直接敲指令whois cmblkg.com，甚至可以找到域名注册者的邮箱、手机、域名所在地等等：

![](https://raw.githubusercontent.com/ouyongchu/dark-tricks/master/images/whois.jpg)
