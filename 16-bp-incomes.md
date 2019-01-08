【EOS42章经】第16章：节点的收入怎么计算？
=======

最近市场行情走势低落，EOS社区中很多人对于EOS出块节点的收入比较关注，今天的部分，就来聊一聊EOS的节点的出块奖励是如何分配的。晚一点我们也会分享社区对于这一问题的讨论。还请继续关注。

本篇只是作为一个基础的小知识点分享，希望当下一次有人问你，EOS的通胀比率是多少，节点的奖励比例是多少，怎么分配的时候，也许这篇文章可以帮你回答这些问题。

主要用到的网站：

- [https://eos.host/mainnet](https://votetracker.eosmedi.com)， 可以直观的查看节点的投票和出块情况
- [https://votetracker.eosmedi.com/](https://votetracker.eosmedi.com/) 可以看到每个节点的投票者的信息

-[https://eosflare.io](https://eosflare.io) EOS网络浏览器

## 超级节点/备用节点/BP是什么？

在许多文章里面你会看到BP这一缩写。这是Block Producer的简称，即出块节点。

实际上，超级节点，这是中文里面才会有的称呼，似乎不加上超级，就显得不够霸气似的。英文语境里面，只是称呼EOS的节点为BP(Block Producer)。

节点分为两类：出块节点，跟备用节点(Block Producer Candidate)。在EOS主网之中，现在是设定为前21个节点为出块节点，其他的节点为备用节点。

备用节点也有另外的名称，叫做候选节点，两个名字都是说的同一回事。

## 节点收益知多少？

通过[https://eos.host/mainnet](https://eos.host/mainnet)这一网络，可以非常直观的查看各个节点的收益情况。

![bp-1.png](https://upload-images.jianshu.io/upload_images/1084915-16cf54f570ff6b4d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

上图列出了前30个节点的得票率占比，橙色为出块节点，灰色为备用节点。

### 21个出块节点的收益

![bp-2.png](https://upload-images.jianshu.io/upload_images/1084915-8d52730450038d81.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

通过第二张图，可以看到，有一栏是列出来了节点的预估收益。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-5581872b8736a551.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 备用节点的收益

![bp-3.png](https://upload-images.jianshu.io/upload_images/1084915-b14761ccef1e4858.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

除了出块节点之外，也有部分备用节点是有收益的。从图中可以看出来，排名59的备选节点hexlantttttt，预计也能够得到100多的EOS作为回报。

你可能会好奇：出块节点的收益跟备用节点的收益是怎么算的呢？我们从EOS的增发开始说起。

##  算算节点的收益分配

### 分配的流程

每次有节点发起指令要领取奖励的时候，系统会计算：

- 新增发的EOS总数有多少；
- 按照比例，将新增发的EOS分配到不同的奖励池之中(下文会详述)；
- 按照节点的实际情况，计算节点应该得到的收益，并分配这部分收益给节点；
- 对于备用节点来说，如果待领取的奖励不足100个EOS，则无法领取奖励。

简单概括就是，先计算各部分奖励池应该分配多少EOS，即新注入多少EOS；然后，根据规则，分配这部分新增的奖励，分配给对应的人节点。

### EOS通胀率为5%

EOS是温和通胀设计的系统，每年增发的EOS比率为5%左右，例如按照总供应量10亿来计算，就是五千万EOS。
而节点得到的奖励占到通胀的一小部分(增发部分的20%)，即总EOS数量的1%。

### 新增EOS的用途

实际上，EOS的增发，是持续进行的，而并非是每年一次性新增加EOS。每次EOS的节点发起领取奖励的命令，就会计算新增EOS的量。
https://github.com/EOSIO/eos/issues/1537
通胀的EOS，有两个用途：

- 通胀EOS的20%,  用于给节点的奖励，即，如果新增了五千万EOS，那么会有1千万EOS分配给所有的节点作为奖励，包括给出块节点和备用节点；
- 通胀EOS的80%， 用于EOS基金池，存在eosio.saving这个账户下，现在仍然没有动用过。

### 出块节点和备用节点的收益

具体的节点奖励的这1%，分为两部分：出块奖励(0.25%)和得票奖励(0.75%)。

出块奖励(BPay)只是分配给出块的前21个节点，而得票奖励(VPay)呢，则是用作所有节点(包括出块节点和备用节点)的奖励。

- 出块奖励占据EOS总量的0.25%，这部分根据节点的出块数量来分配。
假设总量是10亿，那么，出块奖励部分，则是两百五十万 EOS，根据节点的出块数量来计算分配。

- 得票奖励， 占0.75%，这部分由所有节点按照投票权重占比来分配的。

例如，在某个时刻，如果未分配的得票奖励部分是一万2千个EOS，那么，假设 某个节点的投票权重比例为10%，则可以分得10%的奖励，即两千五百个EOS, 另外，作为出块节点，还可以因为出块得到奖励。

## 总结

- 如果某个节点是前21个节点之一，那么，其奖励分为：出块奖励部分 + 得票奖励部分；
- 如果某个节点是备用节点，那么，它可能得到的收益属于得票奖励之中的一部分，比如总共投票权重为100，该节点所得到的投票权重为5，则可以分到得票奖励的5%。
- 如果某个备用节点的得票奖励不足100个EOS，则无法得到奖励。

以上内容可能会有理解不当之处，还请指正。如果有疑问的地方，也欢迎一起交流。

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




 

