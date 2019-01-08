
 
【EOS42章经】第18章: EOS中交易的结构和处理(细节部分)
=====

在EOS中，一笔交易(Transaction)的细节信息是什么？ 这篇文章会对此介绍。

这篇文章内容，可能略显技术性强一点，适合想要对于EOS的交易结构有更多了解的同学。因为个人理解有限，肯定有表述不当之处，还请各位读者多多指教。

## 回顾：EOS中一笔交易的头部信息

[前一篇文章](https://bihu.com/article/1316417702)我们聊到了EOS的交易的结构，分为两部分：
- 交易的头部信息，包含了该交易的一些概况信息
- 交易的细节，包含了其中具体的动作的记录

示例交易id为: `0936c0a15c89caa6d1ac1c7551f9cc9400e06b90656175ea8ec2360a878b2550`

[EOSFlare的链接](https://eosflare.io/tx/0936c0a15c89caa6d1ac1c7551f9cc9400e06b90656175ea8ec2360a878b2550)

[EOSPark的链接](https://eospark.com/tx/0936c0a15c89caa6d1ac1c7551f9cc9400e06b90656175ea8ec2360a878b2550)

一个相对简单的交易的头部信息结构如下所示:

![image.png](https://upload-images.jianshu.io/upload_images/1084915-1ee2320a5a301d35.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

今天内容，接着介绍在交易之中，所包含的更多的细节信息。

## 交易的细节信息

这笔交易，是BetDice的玩家的一笔操作，目的是从账号`crazycapital` 向 `betdiceadmin` 这一账号转账51.1696 EOS。

而这一转账是通过指令来进行的，如下图所示:

![image.png](https://upload-images.jianshu.io/upload_images/1084915-4c023b14dba9b690.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 交易(Transaction)和指令(Action)的关系和区别

指令(Action)是表示单个操作，而交易(transaction, 或者说是事务)是一个或多个指令(action)的集合。

账号和合约之间的通讯是通过指令的形式来进行通信的，可以单独来发送Action，如果想要将多个指令作为整体来执行的话，也可以组合多个指令的方式发送。

### 包含单个指令的交易

`0936c0a15c89caa6d1ac1c7551f9cc9400e06b90656175ea8ec2360a878b2550` 这一笔交易：

![image.png](https://upload-images.jianshu.io/upload_images/1084915-0bc7d75af7555612.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


### 包含多笔指令的交易

如，在Chintai代币租赁平台挂单时候，会发起一笔包含三个指令的交易：
[Bloks的链接](https://bloks.io/transaction/c41f1833bef70dac5a37493a350ec7255d3edbc6baac18b32bea86e86a61e14f)

![image.png](https://upload-images.jianshu.io/upload_images/1084915-c579421c7fdb8f26.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

包含了三笔指令:

- chintailease的prepare指令。为挂单做准备
- eosio.token合约的转账(transfer)指令，转账挂单的金额到合约账户
- chintailease合约的active指令，挂单生效

所对应的原始数据如下所示，这也是EOS中交易结构的细节部分的主要内容:

![image.png](https://upload-images.jianshu.io/upload_images/1084915-acdfb6238b386409.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

 ### EOS指令中所包含的信息

从上面的描述中我们了解到了一笔交易可能包含一个或者多个指令，那么指令的内容是什么呢？

我们再仔细看一下。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-8f7e0746e1fe5838.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

包含了四个部分:
- 所调用的合约，此处为`eosio.token`, 即系统的合约
- 合约中所对应的指令的名称，在这一交易中，调用的合约指令为`trasfer`，即转账的操作
- 所需要的权限，即这一笔转账指令需要得到的授权许可，这里，从`crazycapital`转出EOS，所需要的对应权限为: `crazycapital`的`active`权限。
- 具体的数据，包含了  `from(转出方)`，`to(接收方)`,`quantity(数额)` 以及`memo(备注信息)` 这四者.

综合起来，这一指令表示的是，在`crazycapital`这一账号的授权之下，调用了`eosio.token`合约的`transfer`指令进行操作，从`crazycapital`账号向`betdiceadmin`这一账号(是betdice DApp的合约账号)，转账`51.1696 EOS`, 并在备注之中写明: `action:bet,seed:xjplHOrbMAeV2uLQzS,rollUnder:25,ref:crazymonitor `

下图则展示了对应的原始数据信息:

![image.png](https://upload-images.jianshu.io/upload_images/1084915-215867a257a26446.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


##  EOS中的Action(指令)是如何起作用的？

我们聊多一点关于Action的作用机制。

- 通过客户端(比如钱包)，发起了一笔交易的指令，例如，上例中的`crazycapital`通过钱包在玩游戏的时候，发起了一笔转账，用到了`eosio.token`合约的`transfer`指令；

- 而这一信息会被运行中的节点所接收到，此处为`zb的节点zbeosbp11111`.
- zb所运行的`nodeos`程序, 会将对应的指令请求，转发至`eosio.token`合约所对应的WASM代码，然后这一虚拟机会处理对应的指令，然后继续进行下一指令的操作.

更多的细节，我们后面会在谈到出块部分时候进行介绍。

## 更多: EOS中Action的通信

这部分主要引用自EOSIO开发文档中关于EOS通信模式的说明，技术色彩偏重，如果觉得理解有难度的话，可以安全的忽略，不会影响其他的部分。

EOSIO Smart Contract actions can be called from a user facing UI but at the same time smart contracts can communicate with each other by calling other smart contract actions.

用户可以通过UI来调用智能合约中的指令，另外，不同的智能合约之间也可以进行相互通讯，例如，在一个合约的交易指令之中调用其他合约的指令，或者，在当前的交易之中，使用延迟的方式来触发另外的指令。

EOSIO软件支持两种基本的通讯模式:
- 内联指令，所涉及的交易，通常也称之为内联交易
- 延时指令

### 内联指令(inline action)

在当前指令(action)之中所调用的其他的操作，称之为内联指令(inline action).

例如下图所示:

![image.png](https://upload-images.jianshu.io/upload_images/1084915-cb511ecff7bd12c1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

在从`crazycapital`向`betdiceadmin`转账的这一指令之中，还包含了一个内联的交易(实际上是包含了一条内联的指令)，将对应的EOS数量，从betdiceadmin转给了账号`betdicehouse`.

可以将内联指令看作是当前交易的嵌套的交易，与原始交易的作用域和权限是相同的，并且会与当前的交易一起执行。就是说，从`crazycapital`向`betdiceadmin`转账,和从 `betdiceadmin`转给了账号`betdicehouse`的这两笔指令，会一起执行；如果其中的部分失败了，则所在的交易也会回滚。

无论执行成功或者失败，都不会在交易的范围(scope)之外, 生成通知。

### 延时指令(deferred action)

延时通讯的方式，是指在某个指令之中指定未来某个时刻进行另外某指令，这样的话，会进入排程(scheduled_transactions)，后续由出块节点来决定是否执行，就是说，虽然设定了延时的指令，但是也不确保一定会执行，只能够确定所创建的请求提交是否成功。

## 小结

接着上一篇，今天介绍了交易结构中更多的细节信息，通过这两篇文章，我们对于交易有了细节层面的理解，知道了如何查看交易的信息，并且对于交易的两种通讯模式进行了简单介绍。

这部分内容可能略微难懂，我们的理解也难免会有不当之处，还希望一起交流探讨。

EOS42章经，与你一起学习EOS，一起度过寒冬。

## 文章列表

最近的几篇:

[【EOS42章经】第12章：EOS的RAM，是怎么一回事？](https://bihu.com/article/1761744947)
[【EOS42章经】第13章： EOS运行机制概述及EOS中的transaction(交易/事务)简介](https://bihu.com/article/1550212557)
[【EOS42章经】第14章: 当我们说到TPS时，是在谈论什么？](https://bihu.com/article/1655137720)
[【EOS42章经】第15章: EOS中事务(transacation)的种类知多少?](https://bihu.com/article/1015047260)
[【EOS42章经】第16章：节点的收入怎么计算？](https://bihu.com/article/1926615275)
[【EOS42章经】第17章: EOS中交易(transaction)，包含什么内容](https://bihu.com/article/1316417702)

## EOS42 开创去中心化的未来
 

EOS42的账号为: eos42freedom。
请为EOS42投票，支持我们继续不停开拓去中心化解决方案的未来。





