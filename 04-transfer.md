
【EOS42章经】 第4章: 如何通过钱包操作转账？
====

创建好了账号之后，如何进行第一笔转账操作？
转账到交易所，或从交易所转出EOS到自己到钱包账号中时，需要注意什么？

今天一起来学习EOS转账的操作。

EOS42章经是一系列从浅到深的EOS介绍文章，所以在刚开始的这一周内，我们刻意避开了对一些概念的深入介绍，而是先以实践为主，先用起来。至于具体的概念解释，我们会在后面的文章中展开。欢迎提出你的反馈和建议。

EOS42章经系列，由EOS42节点所创建。感谢你的阅读和支持。

## EOS转账

![image.png](https://upload-images.jianshu.io/upload_images/1084915-9a10f2ee894d78cd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

不同于ETH或者BTC，在EOS中转账是免费的，不需要消耗EOS作为手续费，不过，需要你的账号能够发起交易操作才行。

转账时候，会显示有三个信息要填写：
- 收款人账号，即对方的EOS账号
- 转账金额，即你需要转给他人的EOS的数额，也可以是其他的基于EOS的代币
- Memo，最多可写256个字符，可选择是否填写。

填写好信息后，点击下一步，
![image.png](https://upload-images.jianshu.io/upload_images/1084915-958e306433dace15.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
输入密码，确认后，第一笔转账，就成功完成了。
![image.png](https://upload-images.jianshu.io/upload_images/1084915-1675f878a8300b46.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 如果遇到问题怎么办？

我们之所以操作时候会遇到问题，大多数情况下，是遇到：资源不够用了！
一个EOS账号，就像是一台小电脑，要让这台电脑运转起来，要想发起交易，需要三种资源：CPU，NET和RAM。

如果对应的资源不足，则会无法发起转账。先确认下是遇到什么问题（报错信息会有提示），然后就可以找到对应的解决方案了。

详细可以参考昨天的文章: 
[【EOS42章经】 第3章: 使用EOS转账，你可能遇到的问题
](https://bihu.com/article/1795947835)

###  将EOS转入到交易所，一定要填写Memo
关于Memo，多说一点。
如果你在交易所，比如币安，OKEX, Bitfinex等的时候，除了需要填写交易所的账号地址、转账金额之外，还必须写对Memo。交易所是通过Memo来识别充值到交易所的用户是谁的，往往要求填写一个数字编号。

例如，下图为OKEX的充值EOS时候的界面。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-1bf278ca39329fce.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

因为，所有人充值到交易所，该交易所都是用同一个账号来接受转账的，如果不填写Memo的话，则交易所就无法识别你的身份，从而造成资产损失，不一定能找得回。

因此：将EOS从钱包充值到交易所时候，一定记得填写Memo，并核对好交易所的EOS账号名。

### 从交易所转账到EOS账号

有朋友会疑惑，那么从交易所转出到我自己的EOS账号，是否必须也要填写呢？
从交易所转出到你自己的账号时，是无需填写Memo信息的。个别交易所如果需要填写Memo，还需要参看下交易所的规定。


## EOS可以发起定时转账

使用支付宝还信用卡时候，我们可以设置定时还款，指定未来的某个时间点再转账；使用EOS也是一样，除了即时转账之外，你也可以指定一个未来的时间，进行定时转账。

目前，手机钱包TokenPocket支持了定时转账的功能，这是由EOS的延时交易所提供支持的，而更多的延时交易操作，相信未来会出现。

币乎作者[阿华区块链](https://bihu.com/people/94879)曾经写过一篇关于延时转账的介绍，可以参考阅读:
 [如何发起及取消一笔EOS延迟转账交易](https://bihu.com/article/1881182)

点击转账界面最下边的 「设置交易时间」 按钮
![image.png](https://upload-images.jianshu.io/upload_images/1084915-bf05c656b36708d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

设置计划的转账时间
![image.png](https://upload-images.jianshu.io/upload_images/1084915-4d47eda4215973a0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

确认后，会在页面中显示出来设定的时间。
![](https://upload-images.jianshu.io/upload_images/1084915-e35149cdd6c0a5b7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

然后点击下一步去发起交易即可，不赘述。

## 查询转账交易

转账发出后，可以在钱包中就能查询到交易的记录。如下图所示。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-8855bc25853339a9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![image.png](https://upload-images.jianshu.io/upload_images/1084915-64966ce29c3e0a2b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

除此之外，顺带介绍一下其他几个比较常用的EOS浏览器，也可以查看账号信息，和交易记录。

### 常见的EOS浏览器

- 国内，推荐用: https://eospark.com
除此之外，还有几个主流的浏览器：
- https://eosflare.io
- https://bloks.io

不只是查找交易信息，查询账号信息和合约的信息等，也都可以通过浏览器来查询。

## 概念小结

### EOS中的转账

EOS转账是免费的，不过，EOS账号需要有足够的资源可以发起交易。

EOS中转账是最常见的一种操作类型。转账时候，需要确认好接收者的账号名，金额，如果是转入到交易所，也务必要注意Memo信息要填写正确。

### EOS浏览器

EOS浏览器是用于查看EOS账号细节，交易记录和其他一些相关信息的公开的网站。学习下EOS浏览器的使用，是很有用处的。

如果有遇到任何问题，欢迎留言给我，或者文末扫描二维码，加我微信，邀请你假如EOS42节点的中文官方微信群。

感谢阅读，EOS42章经，陪你一起学EOS，一起过寒冬。

### 文章列表
[【EOS42章经】 第0篇： 初识EOS账号](https://bihu.com/article/1596783525)
[【EOS42章经】 第1章: EOS账号和钱包](https://bihu.com/article/1198397230)
[【EOS42章经】 第2章:  创建你的第一个EOS账号](https://bihu.com/article/1839847881)
[【EOS42章经】 第3章: 使用EOS转账，你可能遇到的问题
](https://bihu.com/article/1795947835)

## EOS42 开创去中心化的未来

EOS42的账号为: eos42freedom。
请为EOS42投票，支持我们继续不停开拓去中心化解决方案的未来。

![vote for EOS42](https://upload-images.jianshu.io/upload_images/1084915-6ed2991946eccf72.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)





