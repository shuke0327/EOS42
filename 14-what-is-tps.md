【EOS42章经】第14章: 当我们说到TPS时，是在谈论什么？
=====

很多人提到EOS的优势时候，会用TPS这个指标来形容：

“比特币的TPS只有7，以太坊的TPS大约在10-20，EOS可以将TPS做到100万”，许多人会这么说。

在这里TPS用作了衡量公链性能的指标，那么，到底什么是tps，代表着什么？EOS能够做到百万TPS么？今天一起聊下这个话题。

## TPS是什么？

TPS，是Transaction Per Second的缩写，表示一个系统每秒可以处理的交易的数量，意味着系统的处理能力和吞吐量。

如果这个系统平均每秒钟可以处理1万笔交易，那么，就是1万 tps; 如果处理100万笔交易，则就达到了百万tps。

### 影响tps的因素

TPS受到多个因素的影响：
- 系统的平均处理时间间隔
- 区块链中每个区块的数据量大小，以及交易数量限制
- 交易的耗时情况

正如上一篇文章中我们所介绍过的，对于EOS的事务/交易而言，可以包含多个动作(action)指令，而包含多指令的一笔交易，所消耗的时间就会更长一些，如果EOS网络中复杂操作增多，则相应的，tps也会收到一些影响。

### TPS高低的影响

如果TPS过低，则会影响到网络的处理能力，造成网络的拥堵，比如加密猫让ETH网络拥堵，就是一例。并且在网络拥堵的时候，对于采用了手续费设计的公链而言，手续费往往会高得离谱。

不过，也并非TPS越高越好，需要结合安全性和稳定性的因素，进行综合考量。目前，EOS的tps峰值数据为3996，不过，也已经是很久之前的事情了。目前由于EOS中复杂类型交易的比例增加，且随着网络CPU设置的自调节机制，会在网络进入拥挤状态时候进行调整，所以当前的EOS网络中tps数量并没有那么高。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-da35d2dbd9da5489.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## EOS的百万TPS，有可能实现么？

离开场景单独看TPS，参考意义并不大，关键还是要看需求。致力于为大规模商业应用落地提供基础设施的EOSIO，为了满足用户的需要，一定的吞吐量是必备的，否则，用户使用体验会很糟糕。

而相比之下，比特币的场景中，对于tps的要求可以没有那么高，当然，这也并不是说目前比特币的tps就足够应对人们的需要了。

另外一个相关问题，经常被人们所提到，EOS所提到的百万TPS是吹牛么？

实际上，在白皮书2.0版本中的描述已经不再是说百万TPS，而是，实现无限的扩展。未来随着跨链通讯技术和侧链技术的发展成熟，通过横向扩展的方式，让更多的相互兼容的区块链协作，还是有可能实现百万tps的数据的。并且，随着其他采用EOSIO软件的同构链的产生，有理由可以相信，TPS这个并不对EOS构成什么限制。而且，随着跨链技术的成熟，当前困扰EOS用户的CPU等问题，也会不再存在。

EOS Weekly是youtube上面的博主，在视频之中，他畅想了EOS的未来实现方式，需要梯子来查看。

视频链接是：
https://www.youtube.com/watch?v=0k5wBa8ELEQ

![image.png](https://upload-images.jianshu.io/upload_images/1084915-04435e50ac3e856d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##  工具：查看EOS网络数据

除了TPS之外，我们还有更好的方式来了解EOS的发展状态，比如:

- 活跃用户量
- 新增用户量
- 交易额度
- DAPP的数量

今天推荐一个小工具，来自SpiderStore的统计工具，列出来EOS主网的数据。
[点击查看](https://spider.store/blockchains/5b6db9013a18fc0012ae2244)

![image.png](https://upload-images.jianshu.io/upload_images/1084915-54cd4a70fee775fa.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

感兴趣的话，你可以跟ETH网络进行一下对比，相信一定会有自己的感受。

## 小结

今天我们介绍了tps这一概念，并且了解了如何使用一个工具，用SpiderStore查看EOS网络的统计信息。

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

