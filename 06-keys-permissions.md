【EOS42章经】 第6章: EOS账号的两把钥匙--认识EOS的权限
=====

上一周，我们一起了解了EOS账号的一些基础知识，并且了解了如何创建账号，如何转账，以及转账时候常见的问题，并且一块分析了EOS账号所常见的问题。

希望通过上周的一起学习，对于EOS的基本操作有了初步的认识。这周开始，我们会稍稍深入一下，介绍关于EOS账号，权限，和交易的一些更深一点的话题。

今天简单聊一聊账号，密钥和权限的话题。

## EOS中的转账

EOS的转账，是从账号转给账号，不是从地址转给地址的。这一点，对于新用户来说也许自然而然，对于从BTC和ETH社区来到EOS社区中的同学，可能不是这样了。

比特币转账，是从一个btc地址转到另外一个btc地址，以太坊也是一样。
但是，在EOS这里，不存在地址的概念；更常用的，是EOS账号。

所以，我们会说:
- 这个`账号`里有xxx个EOS；
- 从账号A向账号B转账
....

而如何管理账号呢？是通过权限来管理的。

## EOS账号的两把钥匙

EOS创建之后，会默认有两个权限，分别成为：Owner 权限和Active权限。
Owner权限，是所有者权限，拥有了这一权限，可以修改账号的所有权，比如在转让账号的时候用得到；
而日常操作中，常用的，是Active权限，你可以理解为是活跃权限权限。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-9bd745ab790c4b29.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


### 权限是用来做什么的？

在EOS中，进行每一笔交易，都需要对应的权限“签字”授权，证明了这笔交易是你有权力发起的。这笔交易才会在网络上被认可。


### 如何获得权限？

权限是跟密钥来绑定的，不同的权限，可以绑定不同的密钥。
创建账号之后，你拥有了一个账号的Active权限所对应的私钥，那么，你将获得了这个账号所对应的Active权限。

这里的讲解比较拗口，实际上，当你操作EOS账号的时候，会发现没那么复杂。只是为了更好的理解EOS账号权限，所以这里才进行介绍。

https://eospark.com/MainNet/account/eos.com

如下图所示：

![image.png](https://upload-images.jianshu.io/upload_images/1084915-f425aa03b2185521.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 账户和公钥的关系

为了进一步说明公钥和账号权限的绑定关系，我们介绍一个知识点：

一个公钥，是可以绑定到多个账户的权限上去。

就是说，如果你有10个账户，都设置了权限acvtive是同一个公钥，那么，你有了这个公钥所对应的私钥的话，就能够操作这10个账户了。

我们来看一个例子： [https://eosflare.io/key/EOS7boot47hMPjKuLGrkvTPi818kkHqMvPWK7483Yfm7PwuJUMca7](https://eosflare.io/key/EOS7boot47hMPjKuLGrkvTPi818kkHqMvPWK7483Yfm7PwuJUMca7)

![image](http://upload-images.jianshu.io/upload_images/1084915-acc50fcf5d5abda2?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

上面的截图，是我用公钥：EOS7boot47hMPjKuLGrkvTPi818kkHqMvPWK7483Yfm7PwuJUMca7
来找到所对应的账号，可以看到，这个公钥，共绑定了22个账号。

##  EOS的私钥可以修改

可以修改EOS权限所绑定的密钥。具体如何修改，这里不聊，后面我们会说到。

EOS的账户默认有owner和active两个权限，每个权限默认会对应一个公钥，那么，如果我的公钥想修改怎么办呢？

其实比较简单，更新账户所对应的权限即可，钱包里面也都提供了对应的操作工具。尤其是通过其他渠道注册(付费请人注册等)，建议最好修改一下所对应的密钥，保证账号的安全。

## 小结

今天主要以概念介绍为主，没有设计到具体的操作。希望通过今天的了解，能够帮你了解到：
- EOS账号中，默认有两个权限
- 拥有了私钥，实际上是意味着获得了账号所对应的权限
- 可以修改绑定的密钥，对权限进行更新

更多内容和问题，欢迎关注我们，也欢迎扫描文末微信，一起进群交流。

## EOS42 开创去中心化的未来

EOS42的账号为: eos42freedom。
请为EOS42投票，支持我们继续不停开拓去中心化解决方案的未来。

![vote for EOS42](https://upload-images.jianshu.io/upload_images/1084915-6ed2991946eccf72.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)







