【EOS42章经】第21章: 交易发送的那一刻，发生了什么： 谈谈交易签名
========

在EOS上发起交易之后，发生了什么？交易如何打包至区块，又上链的？

这个过程虽然短暂，却经过了多道流程。今天开始，我们来聊一聊EOS交易上链到最终成为不可逆这一过程。

限于学识所限，对这部分的理解可能存在诸多不当之处，还请多多指教。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-2feb75608fa1197e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


## transaction 概述

前面部分我们了解过一笔交易的结构。回顾一下：

[](https://bihu.com/article/1316417702)

交易分为两部分：交易头结构(transaction head)，和交易中的actions的信息。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-56008b1003ce169c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

交易之中所包含的Action:

![image.png](https://upload-images.jianshu.io/upload_images/1084915-61fcfb4f9f6bf27f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


那么，在发起交易的时候发生了什么呢？

对EOS的用户来说，主要有如下2个部分：

-  使用钱包服务，为构建好的交易信息签名
-  将签名之后的交易信息发送至EOS网络中

那么， 具体是发送到何处？

钱包服务，不论是使用cleos，还是使用的手机钱包或者Scatter，都会连接到一个运行了nodeos服务的节点。比如，以MeetOne钱包为例：

![image.png](https://upload-images.jianshu.io/upload_images/1084915-21e78fc5932821ce.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

可以看到列出了多个节点。

签名后的交易，会发送至对应的节点，借助于节点，同步至EOS网络之中，进行后续的交易验证，打包入块，区块广播等流程。

今天，我们主要了解这两个部分：

- 交易签名(sign transaction)
- 发送交易(push transaction)


## 交易签名

交易签名的过程，是在幕后发生的，不论你使用的是cleos的命令行工具，还是使用Scatter钱包或者手机钱包，签名只是一瞬间的事情，输入密码，点击确认即可完成。

我们可能会好奇，在幕后发生了什么？

假设我们发起这样一笔交易:

```
从账号`alice`为账号`bob`转出 `20 EOS`的代币
```

会进行两个过程：

- 对交易内容进行摘要处理
- 对摘要处理后的信息签名

### 摘要(digest)

首先，会对交易内容进行摘要(digest)，可以理解为将交易内容进行哈希运算，所用到的算法的是SHA-256 。

在这一步，会将如下三者进行hash处理:

- chain_id, 即交易所在的区块链所对应的chain id，这是考虑了之后的跨链等情况
- 当前的交易
- 可能存在的上下文无关数据(context free data)

顺便说一句，context free data是为了跨链的情形所准备的预留的数据结构，当前的数据之中都不包含这部分内容。

对应的代码，可以参见`transaction.cpp`的文件中，sig_digest的方法：

```
digest_type transaction::sig_digest( const chain_id_type& chain_id, const vector<bytes>& cfd )const {
   digest_type::encoder enc;
   fc::raw::pack( enc, chain_id );
   fc::raw::pack( enc, *this );
   if( cfd.size() ) {
      fc::raw::pack( enc, digest_type::hash(cfd) );
   } else {
      fc::raw::pack( enc, digest_type() );
   }
   return enc.result();
}
```

进行摘要计算后的数据，用16进制表示，大致长这个样子:

`9d8815193d76ee236ef08e8b9fb675e6def3af8d8209d7665540ab9e17944e19`

### 签名

其次，会对这一摘要数据，调用相应权限所对应的私钥，进行签名。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-a19665a91a65f1b9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

EOS使用者，会用到ECDSA算法(Elliptic Curve Digital Signature Algorithm ,椭圆曲线数字签名算法)来对交易进行签名。

而ECDSA算法也分为几种，对EOS而言，常用的是secp256k1曲线的算法，这也是比特币在签名时候所用到的。

感兴趣的话，可以参考:

[https://en.bitcoin.it/wiki/Secp256k1](https://en.bitcoin.it/wiki/Secp256k1)

签名的格式为:

`SIG_K1_K92jkGfvm2UQKtCzxTSVHnMkHQXe2hwtfQdRALjZ2cDSFFGX7DcaAWALbV9pbk5bPnQLDqReEew2qD4uVgmXQYpuEUBJR9`


![image.png](https://upload-images.jianshu.io/upload_images/1084915-16f5db2c80ac4cd6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

通过EOS浏览器，你可以在任何一笔交易之中，见到该签名信息。

而后续在出块时候，出块节点会根据交易之中的这一签名信息，计算出来对应的公钥，对交易进行核验。

至此，我们拆解了签名背后的两个步骤。

下面，就是将签名之后的信息发送到EOS网络之中了。

篇幅所限，后续部分，我们明天接着聊。


## EOS42章经系列

[【EOS42章经】第13章： EOS运行机制概述及EOS中的transaction(交易/事务)简介](https://bihu.com/article/1550212557)
[【EOS42章经】第14章: 当我们说到TPS时，是在谈论什么？](https://bihu.com/article/1655137720)
[【EOS42章经】第15章: EOS中事务(transacation)的种类知多少?](https://bihu.com/article/1015047260)
[【EOS42章经】第16章：节点的收入怎么计算？](https://bihu.com/article/1926615275)
[【EOS42章经】第17章: EOS中交易(transaction)，包含什么内容](https://bihu.com/article/1316417702)
[【EOS42章经】第18章: EOS中交易的结构和通信方式](https://bihu.com/article/1726724387)
[【EOS42章经】第19章: 关于EOS投票的一些知识](https://bihu.com/article/1241672135)
[【EOS42章经】第20章: 简述EOS的区块中包含了什么信息？](https://bihu.com/article/1288213315)


## EOS42 开创去中心化的未来

EOS42的账号为: eos42freedom。
请为EOS42投票，支持我们继续不停开拓去中心化解决方案的未来。

![vote for EOS42](https://upload-images.jianshu.io/upload_images/1084915-6ed2991946eccf72.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)






