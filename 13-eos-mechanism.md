【EOS42章经】第13章： EOS运行机制概述及EOS中的transaction(交易/事务)简介
=====

前面我们介绍了EOS账户中的权限、多签、抵押和赎回，以及基本的EOS资源模型的知识。从这一章开始，我们重点介绍一下EOS的运行机制，今天介绍EOS中的交易的一些细节信息。

我们尽可能避免涉及过多的技术细节，不过，如果你想要交流更多技术细节的话，也可以加我微信(shuke0327，备注：EOS技术)，一起交流。

## 概况

我们先从宏观上概括一下， EOS的运行机制。请注意，这是一个非常简略的描述，我们后续会逐渐展开各部分的细节。

- 用户发起一笔转账操作之后，这一交易会传播到主网之中；
- 当前出块的节点会监听网络之中的交易信息，并进行区块打包、入库、广播等过程；
- 打包节点会确认区块，并开始区块上链的流程，此时区块为可逆状态；
- 每个出块节点每次出块12个，每个区块时间为0.5s时间，就是说，每个BP会出块6s，然后换下一个出块节点；
- 其他的节点也会对区块进行确认；经过两轮确认之后(一轮为precommit验证区块存在，一轮为commit确认状态)，区块会成为不可逆状态(需要得到2/3+1的节点确认). 

![image.png](https://upload-images.jianshu.io/upload_images/1084915-8742d92cd5a0b29a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


- 当前区块高度和不可逆区块高度之间的差值，最大为336，就是由于上述需要两轮确认原因所产生的(由Vitalik进行的提议)，计算如下：
![image.png](https://upload-images.jianshu.io/upload_images/1084915-fdabc733fe0d41da.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

上述概括，参考了[区块链斜杠青年](https://bihu.com/article/1877153)和[EOSFans同学](https://bihu.com/people/274838)的文章，特此感谢。

通过上面的概括，希望能够帮你对于EOS的运行机制有了一个整体的概念。今天，我们接着聊一下EOS中交易(transaction)的一点细节信息。

注意，由于transaction非常重要，因此，今天只是介绍一些直观的基础信息，并不深入展开。

## EOS的基础组成部分：事务和动作(transaction和Action)

在EOS网络中，任何一次与主网交互的操作，都是一笔事务(transaction)，不过，更常用的一个讲法是交易。为了方便起见，在这系列文章之中，我们使用事务这一术语，习惯就好了。

你向他人账户转账时，所发起的是一笔事务；玩游戏时候下注，也是一笔事务..

而一笔事务(transaction)又包含什么呢？可以包含一个或者多个动作。

在一笔事务之中，包含了若干个动作(Action, 也有翻译为指令/操作)。例如，你在Chintai平台发起挂单操作的时候，会包含三个动作:
-  prepare，让chintai合约为挂单做预先的准备工作
-  sent: 将对应的挂单金额发送至chintai智能合约账户
- active: 生效，挂单成功


![image.png](https://upload-images.jianshu.io/upload_images/1084915-8528ca0f2f49b894.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

链接: 

https://eosflare.io/tx/d2a5901ee4b47c02e332738d025b7593895b004e9ba27be3a078dddf2f6b1d82


如果在执行过程中，这一笔交易中的某个动作(action)执行失败了，那么，这笔交易会失败。


### 事务的类别

按照执行时间区分，可以将事务分为：
- 即时执行的事务，不设置延时，发起事务之后立即广播至网络
- 延时事务(delayed transaction), 我们之前也做过介绍

### 事务的延时

默认一笔事务发起之后，是可逆状态的。经过最多336个区块之后，会成为不可逆的状态。

(篇幅所限，明日继续)

## 小结

今天我们介绍了EOS的运行机制的一个宏观概括，并且简约介绍了transaction和action是什么。

如果有什么疑惑的地方，欢迎留言，或者扫描文末二维码进入社群，一起交流。

EOS42章经，与你一起学习EOS基础知识，一起度过冬天。


## 文章列表

[【EOS42章经】 第0篇： 初识EOS账号](https://bihu.com/article/1596783525)
[【EOS42章经】 第1章: EOS账号和钱包](https://bihu.com/article/1198397230)
[【EOS42章经】 第2章:  创建你的第一个EOS账号](https://bihu.com/article/1839847881)
[【EOS42章经】 第3章: 使用EOS转账，你可能遇到的问题](https://bihu.com/article/1795947835)
[【EOS42章经】 第4章: 如何通过钱包操作转账？](https://bihu.com/article/1778822183)
[【EOS42章经】 第5章: EOS账号的安全管理](https://bihu.com/article/1987380753)
[【EOS42章经】 第6章: EOS账号的两把钥匙--认识EOS的权限](https://bihu.com/article/1993549807)
[【EOS42章经】 第7章: 关于EOS的账号的权限：一个通俗解释](https://bihu.com/article/1852766359)
[【EOS42章经】 第8章: 多签是什么？](https://bihu.com/article/1879154878)
[【EOS42章经】 第9章: EOS抵押和赎回是什么？](https://bihu.com/article/1356864332)
[【EOS42章经】第10章: 一文看完关于CPU资源的常见问题](https://bihu.com/article/1015058948)
[【EOS42章经】第11章：工具篇--手把手教你如何使用Scatter桌面版(本文转载)](https://bihu.com/article/1373490838)
[【EOS42章经】第12章：EOS的RAM，是怎么一回事？](https://bihu.com/article/1761744947)


## EOS42 开创去中心化的未来

EOS42的账号为: eos42freedom。
请为EOS42投票，支持我们继续不停开拓去中心化解决方案的未来。

![vote for EOS42](https://upload-images.jianshu.io/upload_images/1084915-6ed2991946eccf72.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


 