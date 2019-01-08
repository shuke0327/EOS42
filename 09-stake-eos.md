【EOS42章经】 第9章:  如何抵押或赎回EOS？
=====

在EOS操作之中经常听到抵押和赎回这两个词。那么，今天的EOS42章经文章，就一起聊一聊这一操作的涵义。

## EOS账户中的资金状态

一个EOS账号之中的资金，分为两种状态：

- 可以转账的部分，是EOS账号之中的可用余额；
- 不能转账的部分，则是处于抵押的状态。

这两部分的数额之和，为该账号中EOS的总额。

[点击查看](https://eospark.com/account/punkneverdie)
![image.png](https://upload-images.jianshu.io/upload_images/1084915-458bf8c9ddf7d00b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

上图中所示的账号 punkneverdie，可用余额为0.301  EOS, 而抵押在CPU和Net上的余额，是0.11 EOS，因此，该账号的总额为0.411 EOS.

## 抵押

抵押，可以理解为将eos“存储”起来。在EOS系统内部，存在一个可靠的“当铺”，将你的EOS抵押之后，这个当铺会提供给你对应的资源，可以根据自己的需要选择换取算力资源(NET)或者是网络资源(NET)。

这个当铺的名字，叫做 “eosio.stake”。通常，会用delegate或者stake的名词，来描述抵押这一行为。


我们查看这个当铺"eosio.stake"账号的时候，其中的额度，就是EOS主网中所抵押的EOS的总量，现在是522,335,249.5148 EOS。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-244ece2f73877c11.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 抵押和投票

跟一些朋友聊天，会对于抵押和投票的关系有一点理解困难，我们在这里一起理清一下概念。

> 投票本身不需要额外占用eos，而是根据你所抵押的EOS的数量来计算投票的权重。

如果你抵押了100个EOS用于获取CPU或者带宽资源，那么，在你投票的时候，这对应的100个EOS，就会换算成相应的投票分值。得到你投票的节点，就会增加这些分数了。

如果你没有抵押EOS，则投票是无效的。如果你所抵押的EOS全部赎回了，投票的权重也会重新计算，变为0.

不过，抵押了之后，也有人会不投票，因此，我们也会看到EOS中抵押率和投票率的差别，就是表示了抵押了但是没投票的那部分EOS的数量。

关于投票的部分，我们后续会专门介绍投票权重的计算，以及BP收益的计算。还请关注。


### 抵押的操作

![image.png](https://upload-images.jianshu.io/upload_images/1084915-998754532073669d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 为他人抵押

一个EOS账号，可以选择为自己抵押EOS，也可以选择为其他账号抵押EOS。
由于EOS设置中，为他人抵押EOS时候有两种状态：租借或者过户，请务必注意，不要选成了“过户”的状态，不然，这部分租借出去的EOS就会被他人所获取了。


## 赎回

抵押状态的EOS是无法随意转账的。

如果需要使用这部分EOS则需要将EOS赎回，相当于，你要从EOS的当铺 "eosio.stake" 这个账户之中，将EOS取回来，而将所获得的CPU/NET资源还回去。

赎回发起之后，这部分数额的EOS所对应的CPU/NET资源就失去了，这时候，是处于赎回状态。并且，需要等待三天的时间，所赎回的EOS才会回到你的账号。
这是为了防止资源被滥用所设置的一个限制。

在赎回之后，你就可以使用这部分EOS了。

以Chintai租赁平台的合约账户 chintailease为例，红框中所显示的这部分EOS，就是正处于赎回状态，赎回将于2018年12月3日完成，回到可用余额的状态。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-317574226b546cb2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


### 赎回期对黑客攻击有防御力么？

我看到过一个说法：“如果你的帐户遭到攻击，你将有3天时间来更改控制你帐户的密钥对”。

不过，如果因为私钥丢失这类情况，则黑客也随时可以改动密钥对，虽然，有部分资金仍然处于抵押状态，但是，这时候你已经失去了账号控制权了，因此，就算eos的资产处于抵押状态，也并不会对于私钥被盗的攻击情况下起到防御作用。

如果有遇到任何问题，欢迎留言给我，或者文末扫描二维码，加我微信，邀请你假如EOS42节点的中文官方微信群。

感谢阅读，EOS42章经，陪你一起学EOS，一起过寒冬。

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

[【技术】针对EOS全历史节点，一个可扩展的解决方案](https://bihu.com/article/1263470421)


## EOS42 开创去中心化的未来

EOS42的账号为: eos42freedom。
请为EOS42投票，支持我们继续不停开拓去中心化解决方案的未来。

![vote for EOS42](https://upload-images.jianshu.io/upload_images/1084915-6ed2991946eccf72.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)








