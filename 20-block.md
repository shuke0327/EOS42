【EOS42章经】第20章:  简述EOS的区块中包含了什么信息？
========

在第17、18章中，我们介绍了EOS的交易的结构，包含交易头部信息和一笔交易所包含的指令信息。

这一章，我们简单聊一聊EOS中区块方面的知识，借助于区块链浏览器看一看EOS的区块包含了什么内容。

后续的章节，会对交易如何广播，节点如何接受交易信息、校验打包区块，以及如何广播区块信息等，进行相应的介绍。

## 给开发者的一份参考文章列表

EOSFans同学之前写了一系列的源代码解读文章，如下几篇，是与区块、交易相关的部分，如果你是开发者的话，这些文章对你更深入理解EOS的机制，应该会有所帮助。

[eos源码赏析（八）：EOS智能合约入门之区块生产](https://bihu.com/article/931992)
[eos源码赏析（九）：EOS智能合约入门之区块打包和广播机制](https://bihu.com/article/965005)
[eos源码赏析（十）：EOS智能合约入门之区块上链](https://bihu.com/article/1014283)

看代码就晕菜的同学也自然不用担心，因为EOS42章经系列就是为了不懂编程的非技术读者所准备的，我们后续会对这其中的机制进行介绍，尽可能让不懂编程的你，也能够多了解一些。

## EOS的主要组成部分

![image.png](https://upload-images.jianshu.io/upload_images/1084915-49787715ff469110.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

上图是摘自EOS文档之中的一个简要介绍，其中：

- cleos是命令行的交互界面，keosd是钱包服务的应用，而实际上对于我们来说，平时所用到的一些钱包，已经将这两者打包好了，我们使用钱包进行操作发起交易即可

- nodeos是出块节点所运行的应用程序，与EOS网络之间进行的交互，就是通过钱包和出块节点所提供的端口进行通讯，而接收到了信息之后，nodeos这一服务，会进行相关的处理，将处理好之后的区块加入到区块链之中。

那么， 在EOS中，区块是怎么组成的？我们一起用浏览器来看一下。

## 查看EOS的区块

![image.png](https://upload-images.jianshu.io/upload_images/1084915-37341d1b3c996322.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

我们可以看到，当前EOS主网已经产生了3千1百多万个区块了。EOS的出块是每0.5s中创建一个块，每个超级节点会持续产生12个区块，然后换下一个出块节点。就是说，每个节点会出块6s中，一轮下来，就是126s的时间(6s * 21个出块即节点)。


![image.png](https://upload-images.jianshu.io/upload_images/1084915-a6b0126c0e1edd54.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

[EOSQ](https://eosq.app/blocks)是EOS Canada节点所创建的一个EOS浏览器。上图中直观列出了区块和区块中所包含交易数量的状态。

如果区块之中不包含交易，就称之为空块；而每一个区块之中所包含的交易数量也是会收到出块时间的限制，每个区块目前实际的可用时间为0.2s。

## 区块中所包含的信息

[链接](https://bloks.asia/block/31529592)

### 区块概要信息

![image.png](https://upload-images.jianshu.io/upload_images/1084915-eb54c0fc89f2abe5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如图所示，我们可以看到，列出来了如下的信息:

- 当前的区块编号
- 区块ID，是一串hash字符串，使用了sha的算法
- 时间戳
- 该区块的出块节点

除此之外，在EOS Bloks的浏览器中，还列出来了更多的额外信息:
- 计划版本，表示当前的出块节点的排期
- 事务数量：即，当前区块之中的交易数量
- 操作数量，即所包含的action的数量

除了列出来的这部分数据之外，实际上，在EOS的区块链上，还会列出来如下的部分:

- 前一个区块的ID
- 交易的merkle树的根节点的hash值
- 指令(action)的merkle树根节点的hash值
- 出块节点的签名信息(producer_signature)

![image.png](https://upload-images.jianshu.io/upload_images/1084915-0ad4f4f95570f061.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 交易数据

除了区块头数据之外，一个区块之中接下来的部分，会列出来区块中所包含的交易的信息。

在不同的浏览器中，所展示的样式自然是有所不同的，不过对于区块链有一些了解的同学应该能够清楚，这部分的做法，和比特币区块中的显示是相似的。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-465af3a073d8a3b6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 原始数据

借助于EOSPark所列出来RAW数据显示，截图如下:

![image.png](https://upload-images.jianshu.io/upload_images/1084915-a493711cf29aca84.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

[链接](https://eospark.com/block/31529592)

## 小结

今天的内容相对简单一点，通过使用EOS浏览器对EOS的区块进行查询，我们一起查看了EOS中区块的大致结构，希望能够帮你有一个直观的印象。后面的文章中，我们会继续聊一聊EOS的交易如何组装成为区块，区块又是如何验证广播上链的。

感谢您的阅读和支持，EOS42章经，与你一起了解EOS的小知识，一起度过冬天。

## 文章列表

最近的几篇:

[【EOS42章经】第12章：EOS的RAM，是怎么一回事？](https://bihu.com/article/1761744947)
[【EOS42章经】第13章： EOS运行机制概述及EOS中的transaction(交易/事务)简介](https://bihu.com/article/1550212557)
[【EOS42章经】第14章: 当我们说到TPS时，是在谈论什么？](https://bihu.com/article/1655137720)
[【EOS42章经】第15章: EOS中事务(transacation)的种类知多少?](https://bihu.com/article/1015047260)
[【EOS42章经】第16章：节点的收入怎么计算？](https://bihu.com/article/1926615275)
[【EOS42章经】第17章: EOS中交易(transaction)，包含什么内容](https://bihu.com/article/1316417702)

## EOS42 开创去中心化的未来

![vote for EOS42](https://upload-images.jianshu.io/upload_images/1084915-6ed2991946eccf72.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

EOS42的账号为: eos42freedom。
请为EOS42投票，支持我们继续不停开拓去中心化解决方案的未来。




 