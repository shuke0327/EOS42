
【EOS42章经】 第8章: 多签是什么？
=====

在许多关于区块链的文章之中，你会听到“多签”这个词，那么，EOS区块链中多签是什么呢？

今天EOS42章经的内容，我们一起来聊一下多签，权限的阈值，权重等概念。希望有助于理解。

## 多签是什么？

前面我们提到，发起一笔交易需要得到账号的授权，就像是给一张支票盖上公章，这张支票才有效。

而在多签的情况下，一笔交易，需要经过多人的同意，才可以生效，比如，如果你想要买一台PSP，那么，自己同意了不算，也得经过女朋友或者老婆大人的同意才行。

另外一个比喻，来自[阿华区块链](https://bihu.com/article/1585302):

> 多签，类似于一个保险箱上了两把锁（或更多），需要两把钥匙（或更多）同时才能打开。

默认情况下，用一把锁就够了，只需要一把钥匙就可以授权交易；不过，在一些重要的交易类别中，就需要用到多签了。

例如，我们在EOS社区之中通常会听到这样的新闻： 某个提案，需要经过前21个节点之中的15个签名，这一提案才能够通过。这种场景，用到的就是多签。

再如，为了提升账号资产的安全性，可以将账号的权限修改为多签，进行对应操作的时候，需要用多个钥匙进行解锁/授权，才能够发起交易。

### 多签的案例: chintai租赁平台

EOS42创建的EOS资源租赁平台 Chintai，其智能合约账户就是一个设置了多签保护的例子。

https://eosflare.io/account/chintailease

![image.png](https://upload-images.jianshu.io/upload_images/1084915-1c3596e79bb7398b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

chintailease这个账号的权限，由主网上的11个节点(出块节点或者备用节点)来共同保护，如果需要调用owner权限，则需要11个节点之中的6个节点共同签名授权，才可以。借助这样的方式，来确保了平台不会因为单个账号的私钥遇到问题，而遭到攻击。

Chintai的多签账户若想攻破，有两种方式，要么贿赂了Chintai的11个BP赞助者中的至少6个，形成合谋，或者，一个黑客获得11个私钥中的6个而将Chintai账户攻破。如果检测到有任何的恶意活动，Chintai还有一个“暂停”功能，可用于快速锁定平台。

此外，假设说Chintai的这11名赞助者中有6名都被贿赂了，在这种情景下有理由推断，整个EOS网络也都会受到威胁了。如果你相信你的个人账户中的EOS是安全的，那么， 你也有同样的理由相信Chintai 的安全性，因为 Chintai 也得到了同样的安全保障。

更多的介绍，可以参考: https://bihu.com/article/1510040


## 权限的阈值和权重

![image.png](https://upload-images.jianshu.io/upload_images/1084915-1c3596e79bb7398b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

多签涉及到了两个核心的概念：

- 阈值(threshold)，默认为1. 在上图之中，chintailease的owner权限的阈值是6；
- 权重(weight), 默认为1.  对chintailease具有共同控制权的这些账号，他们各自权限所对应的权重为1.

这就意味着，需要调用owner权限的时候，至少需要权重 >= 6才可以，因为每个账号的权重为1，就意味着需要6个账号一起授权，才能够调用owner权限。

我们做个假设(下图只是为了更进一步说明阈值和权重的关系，不是真实的情况)：

![image.png](https://upload-images.jianshu.io/upload_images/1084915-79214941b6205d7e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如果将前三个账号权限所对应的权重从1，修改为2，而阈值不变，仍然为6，则，只需要前3个账号权限来授权,（2+2+2）, 就可以符合阈值的要求了。

## 扩展：如何设置多签？

现在的手机钱包，大多数仍然没有提供多签的功能。不过，你可以通过Scatter插件钱包 配合网站工具的方式，来实现多签。

如果懂一些编程的话，多签也可以通过命令行界面来设置，出块节点们就是这么做的。

### 设置多签的流程

1\.  将账号权限改为多签权限

默认情况下，一个账号的权限都是只绑定了一个公钥的。如果需要采用多签的方式，首先，要将账号的权限改为多签的方式。

比如，我们将某个账号的active权限的阈值修改为2，并且，绑定两个公钥，每个公钥所对应的权重设置为1.

默认情况下的账号：

![image.png](https://upload-images.jianshu.io/upload_images/1084915-2ac6ded5c49708c8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

修改为多签之后的账号：

![image.png](https://upload-images.jianshu.io/upload_images/1084915-39155e91da409f77.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

2\. 创建多签交易
3\. 多个公钥/账号的权限分别签名
4\. 提交多签交易。将签名之后的交易，发送到区块链上。

这是多签的基本流程。

### 实例参考

文末附上一个教程，是币乎作者[阿华区块链](https://bihu.com/people/94879)所写的一篇教程，使用Scatter + eostoolkit的方式，来设置多签。

感兴趣的读者，可以参阅： [手把手教你设置EOS的多签转账功能（附实例）](https://bihu.com/article/1585302)


## EOS42 开创去中心化的未来

EOS42的账号为: eos42freedom。
请为EOS42投票，支持我们继续不停开拓去中心化解决方案的未来。

![vote for EOS42](https://upload-images.jianshu.io/upload_images/1084915-6ed2991946eccf72.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

