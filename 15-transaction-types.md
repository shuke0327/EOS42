【EOS42章经】第15章: EOS中事务(transacation)的种类知多少?
====

在EOS网络中，你发起的任何一个操作，都是一笔事务(transaction)。这是EOS网络之中的重要组成部分之一，事务在EOS网络之中传播，由出块节点对事务的验证、执行、打包，并最终加入到EOS区块链网络之中。

如果将EOS的区块链网络，理解为一个大的账本，这个账本的每一页，代表了一个区块，那么，一笔事务(transaction)就是其中的一条记录。这一个大账本在全球各地传播，每个人都可以获取并验证，而其中最基础的部分，就是事务了。

提到transaction，一个更常见的提法是交易。在谈及transaction的这系列文章之中，我们使用事务这一术语；而提到交易，会专指转账类型的操作。

##  1. 一笔事务中，包含一个或者多个动作(Action)

在一笔事务之中，包含了一个或者多个动作(Action, 也有翻译为指令/操作)。常见的转账操作，只包含一个动作。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-c677a875d25cb845.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

不过，也有一些更复杂的操作，会包含多个动作。

例如，你在Chintai平台发起挂单操作的时候，会包含三个动作:
-  prepare，让chintai合约为挂单做预先的准备工作
-  sent: 将对应的挂单金额发送至chintai智能合约账户
- active: 生效，挂单成功


![image.png](https://upload-images.jianshu.io/upload_images/1084915-8528ca0f2f49b894.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

链接: 

https://eosflare.io/tx/d2a5901ee4b47c02e332738d025b7593895b004e9ba27be3a078dddf2f6b1d82


如果在执行过程中，这一笔交易中的某个动作(action)执行失败了，那么，这笔交易会失败。


##2.  按时间划分：即时执行事务，和延时事务

按照执行时间区分，可以将事务分为：
- 即时执行的事务，不设置延时，发起事务之后立即广播至网络
- 延时事务(delayed transaction), 我们之前也做过介绍

延时事务，意味着你可以指定这一笔事务什么时候执行。目前，手机钱包TokenPocket支持了定时转账的功能，这是由EOS的延时交易所提供支持的，而更多的延时交易操作，相信未来会出现。

币乎作者[阿华区块链](https://bihu.com/people/94879)曾经写过一篇关于延时转账的介绍，可以参考阅读:
 [如何发起及取消一笔EOS延迟转账交易](https://bihu.com/article/1881182)

点击转账界面最下边的 「设置交易时间」 按钮
![image.png](https://upload-images.jianshu.io/upload_images/1084915-bf05c656b36708d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

设置计划的转账时间
![image.png](https://upload-images.jianshu.io/upload_images/1084915-4d47eda4215973a0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

确认后，会在页面中显示出来设定的时间。
![](https://upload-images.jianshu.io/upload_images/1084915-e35149cdd6c0a5b7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##3. 常见的事务类别

EOS Authority发了一篇文章，介绍了EOS中常见的transaction类型，见[EOS Authority博客](https://eosauthority.com/blog/types_of_transactions_on_eos_accounts).
概括如下：

### 1. 创建账户

在EOS网络上创建的每个帐户都需要一些RAM来存储帐户名称、密钥以及与帐户连接的其他重要信息。因此，通常情况下，每个新帐户交易都要立即伴随着“购买RAM”操作。通常，为了让新创建的账号能够使用，也会为该账户抵押一定的资源(CPU和NET)，因为这些是新账号发起任何一笔事务时候所需要用到的。

请记住，由于无法删除帐户，所以创建账号时候所消耗的这部分RAM都是永久锁定的。

### 2. 购买RAM的事务

由于需要在EOS区块链上存储数据，会占用RAM资源，所以购买RAM也是常见的操作。

更细节一点，购买RAM可以有两种方式，分别是不同的单位：指定你所需要购买的RAM的字节大小，或者，指定要用多少数量的EOS来购买RAM。

### 3. 抵押带宽资源/赎回带宽资源

CPU和NET资源，经过我们前面的介绍， 应该你已经不陌生了。抵押带宽操作可以指定要分配的CPU或网络带宽的数量。当你抵押之后，会立即分配给你对应的资源，如果需要赎回的话，你需要等待3天的时间。

与此相关的是，你的投票权会根据你抵押在CPU和网络资源的数量来计算。

### 4. 投票

这一操作，主要是用来投票选择出块节点时候执行的。你的投票权会根据你抵押在CPU和网络资源的数量来计算。并且，会存在投票权的衰减，这也是最好隔一段时间更新一下投票的原因。

最多你可以为30个账号投票，或者，你也可以将投票权委托给代理，让它帮你投票。

### 5. 转账(transfer)

当查看你账户的历史交易记录时候，转账操作是最常见的一类。除了转账EOS之外，也可以将空投的一些代币进行转账操作，实际上，空投，就是代币账号根据一定的条件筛选，设定好数量之后转账给你的过程。

### 6. 账户权限更新

要对账号的权限进行更新，需要修改对应的密钥。账号权限默认为两类：所有者权限，和active权限。如果你自己没有操作，却发现账户权限有更新记录，那么，往往意味着密钥泄漏被黑客更改了权限了。

另外，也可以自己设置自定义的权限类别。

### 7. 其他操作

除了上面列出来的这些常见类别之外，你在玩游戏或者使用其他 DAPP时候也会有各种其他类型的事务产生，这些是与相应的智能合约相关的。如果有疑问的地方，也欢迎一起交流。

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

