【EOS42章经】第10章: 一文看完关于CPU资源的常见问题
=====

目前使用EOS账号时候，最经常遇到问题的是：CPU资源的问题。那么，今天的EOS42章经的内容，我们就一起来聊一聊关于CPU的一些常见问题。

并且，本篇文章会告诉你，也许在未来不久之后，作为重度游戏玩家的你，可以不必再担心CPU的问题了，先知道为什么嘛？

## 1. CPU用完可恢复么？

CPU资源用完可恢复，周期为24小时

CPU和NET资源是可恢复资源，而RAM是占用的资源。

如果你看到自己已经很久没有使用EOS账号，但是却发现CPU的已用量仍然很大时，只需要新发起一笔交易，这一使用数据就会更新了。

这是因为，当CPU和带宽资源用光后，会进行线性恢复，24小时后，会完全恢复。但是，由于系统不会主动进行计算，需要在你新发起一笔交易之后，才会重新计算你的已用资源的量。

阿华的这篇文章，详细解释了CPU的计算方式，推荐想要继续研究的读者，可以参考:

[EOS上CPU/带宽资源使用量是如何计算的](https://bihu.com/article/1794010054)


## 2.  每一笔交易都需要消耗CPU资源

CPU和网络资源，相当于是每一笔交易的燃料。CPU是以时间为单位来衡量的，而带宽资源(NET)是以字符数(bytes)来衡量的。

EOS账号中每一笔交易，都需要用到CPU，你需要为每一笔交易“买单”。

可以通过浏览器来查看(目前，EOSflare跟bloks两个网站可以显示出来每一笔交易的资源消耗情况)

https://bloks.io/transaction/4d8b6639e78303d166234dd2721a6670da324d36b7efefb3e9be3b7d5886fedb

![image.png](https://upload-images.jianshu.io/upload_images/1084915-cfe5c37787246be6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

图中可见，该笔交易消耗了719 μs的CPU资源，	144 Bytes的网络资源。

## 3. 交易所消耗的CPU使用量，由超级节点来开出账单

超级节点在创建区块的时候，会将这笔交易进行计算，在这过程中消耗了719 μs的CPU资源，	144 Bytes的NET资源，就是为这笔交易所记下的“账单”， 会记录在交易的数据结构之中。

而这一份账单，其他的节点都会认可，也留在了区块链上。

这份账单谁来买单呢？

### 未来：可能普通用户不必再担心CPU问题

目前情况下，是由交易的发起者来买单的。比如，A账号向B账号转账，这一笔交易的CPU消耗和NET消耗，会算作A账号的，并从A账号的CPU和NET可用余额中，扣除对应的部分。

而未来你读到这篇文章的时候，可能已经有了另外一种方式，由接受者买单，因为BlockOne的开发者已经在进行这一功能的开发工作了([请查看](https://github.com/EOSIO/eos/issues/6332)).

例如，你在玩游戏的时候，目前向游戏中转账，需要消耗的是你自己的资源，这也是导致目前许多游戏玩家抱怨CPU不足卡顿的原因；而在接收者买单的选项出现之后，也可以由DAPP项目方来承担相应的CPU开销，为用户的游戏买单。

这样，普通用户就再也不必担心CPU的问题了。

## 4.  CPU需要抵押来获得，且“价格”会波动

（如果你还不了解如何操作抵押，那么，可以找到你所用钱包的客服咨询询问。或者查看这篇文章: ）

既然每一笔交易都需要用得到CPU资源，那么，如果你的CPU资源不足，自然就无法发起交易。正如昨天我们一起了解到的，需要抵押EOS到“当铺”(eosio.stake这一系统账户)，然后获得对应的CPU资源。

抵押了同样数量的EOS，具体可以得到多少的CPU资源，是会根据EOS网络的忙碌程度来变化的；如果CPU使用的高峰期，则获得的资源就少，如果是空闲时候，获得的资源就更多。

本质上，CPU的“价格”，是用于调节网络拥堵程度的一个工具。
（注意：用CPU“价格”这一说法只是为了方便你的理解，实际上，因为你抵押多少EOS，就可以赎回多少EOS。不会因为CPU价格变动而导致所赎回的EOS数量变少，之后文章，我们会详细介绍CPU跟RAM这类资源的不同。）

感兴趣可以查看EOS Titan所提供的一个工具，方便你直观的了解CPU“价格”的变化。


![image.png](https://upload-images.jianshu.io/upload_images/1084915-6170ffc9af242a2e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

工具: https://voters.eostitan.com/labs

## 5. 其他相关问题

### 如何知道EOS一笔交易需要消耗多少资源？

EOS NewYork提供了小工具 EOS Charge，可以展示出来常见操作所需要的CPU资源和NET资源的用量,网址为: https://www.eoscharge.io/

![image.png](https://upload-images.jianshu.io/upload_images/1084915-6e810be1a92c2e27.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

也可以查看 阿华区块链的文章: [EOS账户需要抵押多少CPU资源](https://bihu.com/article/1786663)

### 在CPU已经不够的时候，该如何操作？

EOS设计中存在一个状况，就是，当CPU不足的时候，是无法发起操作，为自己抵押CPU的。如果遇到这种情况，可以参考这两篇文章中的解决方案:

[CPU不够怎么办：写给CPU“红人”的极简解决方案](https://bihu.com/article/1868214)

[常见的几种CPU资源租赁方式](https://bihu.com/people/94879)

### 更多问题

如果有遇到其他的关于EOS的问题，也欢迎留言给我，或者文末扫描二维码，加我微信，邀请你假如EOS42节点的中文官方微信群。

感谢阅读，EOS42章经陪你，一起学EOS，一起过寒冬。

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


## EOS42 开创去中心化的未来

EOS42的账号为: eos42freedom。
请为EOS42投票，支持我们继续不停开拓去中心化解决方案的未来。

![vote for EOS42](https://upload-images.jianshu.io/upload_images/1084915-6ed2991946eccf72.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)