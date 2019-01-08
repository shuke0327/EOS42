【EOS42章经】第17章: EOS中交易(transaction)，包含什么内容
========

EOS42，与你一起学习EOS，一起度过寒冬。EOS42节点，期待得到你的投票支持。
 
在EOS 区块链之中，交易与账户是密不可分的．之前我们已经对于账户创建，账户和密钥，账户权限等内容进行了介绍，今天，就聊一聊EOS的交易结构是什么样子的。



这一篇文章中的内容，可能对你来说略微陌生一些，我们会一起看看在一笔转账交易的背后，在区块链中所记录的信息会是什么样子，会包含哪些部分。

## 查看EOS交易的工具

最早的时候，一个网站是eostracker，可以查看EOS的交易，网址是: [http://eostracker.io/](http://eostracker.io/)，算是最早的一批EOS浏览器之一了。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-2e6b564937874f79.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

当时EOS还没有上线，工具及相应网站并不多，不过现在，你可以有更多的选择了。

如果感兴趣这个史前时期的网站是什么样子，今年三月的时候，我曾经写了一篇帖子，提供了 eostracker 的更多的细节:  [想直观了解EOS长什么样? 这个网站不可错过](https://bihu.com/article/123275)

目前而言，推荐用如下几个EOS浏览器来查看：

### EOS Park
https://eospark.com

![image.png](https://upload-images.jianshu.io/upload_images/1084915-0e188d2ca49ce6f4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### Bloks
https://bloks.io/
由EOS CafeBlock和EOS HK一起创建。现在也提供了亚洲版:
https://bloks.asia/ 无梯子访问流畅

![image.png](https://upload-images.jianshu.io/upload_images/1084915-d000b8bd2e4af63c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


### EOSFlare
https://eosflare.io
![image.png](https://upload-images.jianshu.io/upload_images/1084915-0a0085ecd121aaeb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 交易(transaction)的结构，长什么样子

介绍了上面的工具之后，我们就可以学习如何用这些工具来查看一笔交易的结构之中包含什么内容了。

一笔交易，会包含两个主要部分：
- 交易的头部信息，包含了该交易的一些概况信息
- 交易的细节，包含了其中具体的动作的记录

由于篇幅所限，我们拆解为两个部分。今天这篇文章所提到的这些信息，主要来自于交易结构之中头部。

为了便于理解， 在这篇文章里面我们就不用原始格式的交易的信息，而是以在浏览器中经过解析之后的信息来表示，这部分是更多的非技术读者所经常遇见的。这篇文章中的概括，如果能够帮你理解这些分别代表着什么内容，就达到目的了。

在文章末尾，会附上原始的记录。看看在区块链上，这些信息是以什么样子来呈现的。不必深究，更常见的情况下，你是通过EOS浏览器来查看的解析之后的结构数据。

我们以id为`0936c0a15c89caa6d1ac1c7551f9cc9400e06b90656175ea8ec2360a878b2550`的这一笔交易为例，介绍一下一笔交易之中所常见的一些信息代表了什么意思。




[EOSFlare的链接](https://eosflare.io/tx/0936c0a15c89caa6d1ac1c7551f9cc9400e06b90656175ea8ec2360a878b2550)

EOSFlare的信息表示，比较适合此处的表述，因此，这里主要用eosflare来介绍。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-a64828aaba0ab730.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如上图所示，我们可以看到包含了如下的内容：

###  一笔交易的交易ID

在这里，就是`0936c0a15c89caa6d1ac1c7551f9cc9400e06b90656175ea8ec2360a878b2550`

在任何一个EOS浏览器中输入这一串ID，即可以找到区块链上这一笔交易所相关的信息了。

例如，下图是在eospark所查询的结果:
![image.png](https://upload-images.jianshu.io/upload_images/1084915-fe1bade7cbf775c8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


### 交易的状态

交易是属于待确认状态，还是已经确认的状态(即不可逆转)。交易广播到区块链中之后，需要经过两轮的节点确认(大致最长时间为3分钟左右,336个区块)，然后一笔交易才会成为不可逆的状态。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-0934ddd29e513d79.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###  交易时间

![image.png](https://upload-images.jianshu.io/upload_images/1084915-813bb3c9cd7d9d2e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


分为区块时间，与过期时间。区块时间是指，交易所处的区块 `31027365` 的时间，而过期时间是在该笔交易发起之后，如果由于网络等原因导致交易被执行的时候超过了这一时间，则交易就会成为无效状态，无法计入到区块链上。

### 交易的参考区块

![image.png](https://upload-images.jianshu.io/upload_images/1084915-4eb8d9693e1a6bee.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

你可能会好奇，这是代表了什么意思呢？实际上，这是代表了一个以往的区块。

在EOS的设计之中，采用了名为TaPoS(Transaction as Proof of Stake)的机制, 简单来说，就是每一笔交易的信息之中，都会包含了一个区块的信息记录，实际上，在交易结构之中的表述是`ref_block_num`和`ref_block_prefix`这两个字段。不过这两者只是表示方式不同而已，仍然指的是同一个区块。

这里的`ref_block_num`和`ref_block_prefix`并不一定是指的最近一个区块的区块头，而是指所引用的区块编号(数字)，以及区块头的前缀(hash值的一部分)．

`ref_block_num(参考区块号，即此例中的28831)`, `ref_block_prefix(参考区块的前缀)`和`expiration(过期时间)`三者是用作TaPOS(Transaction as Proof of Stake, 交易作为权益证明)算法，是为了确保一笔交易在所引用的区块之后和交易过期日期之前能够发生．在steem跟bts中，也有相同的设计．

### 交易所消耗的资源状况

EOS Cafelock和EOS HK节点所创建的Bloks是一个很流行的EOS浏览器, 其中列出了[一笔交易所消耗的资源详情](https://bloks.asia/transaction/0936c0a15c89caa6d1ac1c7551f9cc9400e06b90656175ea8ec2360a878b2550)

![image.png](https://upload-images.jianshu.io/upload_images/1084915-6136e0d9200464de.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

可以看到，这一笔交易中，消耗了CPU: 1.839ms, NET: 192字节。另外，RAM的消耗也计算了出来。由于在交易的原始数据之中，并不会列出RAM的消耗情况，这里应该是Bloks所另外做的计算。至于RAM的消耗的计算机制，还需要请教Cafe的同学解释了。

(另外值得注意的一点是，此处Bloks所列出的NET的字节消耗量，跟EOSFlare和交易元数据之中所列出的数据有所差异，感兴趣的可以继续去探索。)

在EOSFlare之中的显示是：

![image.png](https://upload-images.jianshu.io/upload_images/1084915-d7e886713627beed.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 交易是否为延时交易

![image.png](https://upload-images.jianshu.io/upload_images/1084915-8b0906355d053310.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

由于EOSPark与EOSFlare之中，对于非延时的交易并没有相应的表示，所以此处用了来自Bloks的页面，其中列出来，该笔交易的延时时间为0，就是说，这是一笔即时的交易。



### 交易头部的原始信息

[来自EOSPark所展示的原始信息](https://eospark.com/tx/0936c0a15c89caa6d1ac1c7551f9cc9400e06b90656175ea8ec2360a878b2550)

![image.png](https://upload-images.jianshu.io/upload_images/1084915-3af5df32272dce11.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这里列出了交易的头部结构之中的相对应的信息结构。可以看出，我们前面所提到的在EOS浏览器中所展示的一些信息，绝大部分都是来自于这一原始记录。

##  后续: 交易之中的Action的细节

下一篇，我们继续解读余下的部分，并且介绍什么是内联交易(inline transaction)。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-e58fbcdc9e2f0d13.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如果有感兴趣的地方，或者由于我个人理解有误所造成的错误表述，还请指正和探讨。欢迎扫描文末微信二维码，加我微信，一起交流。

EOS42，与你一起学习EOS，一起度过寒冬。EOS42节点，期待得到你的投票支持。

## 文章列表

最近的几篇:

[【EOS42章经】 第8章: 多签是什么？](https://bihu.com/article/1879154878)
[【EOS42章经】 第9章: EOS抵押和赎回是什么？](https://bihu.com/article/1356864332)
[【EOS42章经】第10章: 一文看完关于CPU资源的常见问题](https://bihu.com/article/1015058948)
[【EOS42章经】第11章：工具篇--手把手教你如何使用Scatter桌面版(本文转载)](https://bihu.com/article/1373490838)
[【EOS42章经】第12章：EOS的RAM，是怎么一回事？](https://bihu.com/article/1761744947)


## EOS42 开创去中心化的未来

EOS42的账号为: eos42freedom。
请为EOS42投票，支持我们继续不停开拓去中心化解决方案的未来。

![vote for EOS42](https://upload-images.jianshu.io/upload_images/1084915-6ed2991946eccf72.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)









