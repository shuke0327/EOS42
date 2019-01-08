【EOS42章经】 第7章: 关于账号的权限的一个通俗解释
====

今天继续了解EOS的权限的话题。

## 提醒

今天看到多个钱包的提醒，由于APP的证书到期，可能会导致更新钱包之后，需要重新导入私钥。提醒各位EOS钱包的用户，如果还没有做好私钥备份的，请务必确认先进行私钥备份，避免因为丢失私钥而造成的资产损失。


## 授权，就是给支票盖章

### 一笔交易就是一张支票

如果将EOS中的一笔交易，理解为一张支票，上面写明了从A向B转账多少的信息；
那么，有权力给这张支票盖章许可这一笔交易的，就涉及到对应的财务的权限了，只有财务盖章批准了，这张支票才可以生效。

### 对交易的授权

而财务章锁在一个保险箱之中，如果要盖章，需要用一把钥匙打开保险箱，取出来这个财务章，然后为这笔交易盖章，这就是授权的过程。

而这把钥匙，在EOS中对应的，就是私钥。
有了私钥，就得到了授权交易的权力。

不过，故事到这里还没有结束。因为这把钥匙，还只是管着财务的权限。那么，如果要替换掉财务呢？

### EOS的两把钥匙

在另外的一个抽屉里，放着的一个保险柜，只有公司老板才有钥匙来打开，里面放着的是公司的最重要的印章。

这枚印章，类似于古代帝王的玉玺，是一个账号的所有权的象征。你可以用这个权限来更改所有权，也可以用这一权限，来炒掉财务的鱿鱼。

借助这一比喻，对应到EOS之中呢？

昨天我们也聊到了EOS账号中存在两把钥匙：owner 权限(所有者权限) 和 active权限(操作权限)。

在上面的故事中，财务的权限，是对应着active权限，有权力进行除了更换所有者之外的所有的操作。

而owner权限是什么呢？就是公司的老板所拥有的这个印章对应的权限，可以用这个权限，来替换掉财务，即，更改掉active权限；同时，也可以转让公司的所有权，即，更改owner权限。

补充一点：往往通过钱包和别人帮忙所创建账号，owner权限跟active权限的私钥是同样的，就是说，是用了同样的锁来管理。只要有一把钥匙，就可以使用这两个权限了。

另外，由于修改账号权限的操作有一定的风险，所以，建议要熟悉之后才考虑操作，并且，在进行账号修改权限操作之前，一定要做好对应私钥的备份。

## 如何查看自己的权限

### 一个检查账号安全性的网站

一家安全公司 派盾(PeckShield)提供了一个检查EOS账号安全性的工具。可以输入你的账号名，检查是否存在安全的隐患。

该工具是 [https://peckshield.com/eosrescuer](https://peckshield.com/eosrescuer)

网站上对于该工具的说明：

> 由于一些EOS钱包采用强度较弱的助记词组合，用户生成的秘钥极易遭受“彩虹攻击”——被黑客暴力破解密码。为保护受影响的EOS用户，派盾(PeckShield)紧急提供了 EOSRescuer 安全服务！

输入账号名，点击检测。

![image.png](https://upload-images.jianshu.io/upload_images/1084915-0d91aba32adf2e2f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如果发现检测结果提示密钥有问题，你需要尽快修改。如果需要指导，可以扫描文末的二维码，加我微信告诉你怎么做。

请注意，这个工具仅仅是用来检查你账号权限的密钥是否存在问题的，并不代表着，你就可以忽略其他的风险了。安全是一个系统性的工程，需要做好各方面的保护措施才行，之前我们写过一篇文章，介绍了一些常见的问题，可以阅读：

[【EOS42章经】 第5章: EOS账号的安全管理](https://bihu.com/article/1987380753)

### 通过钱包即可查看

![image.png](https://upload-images.jianshu.io/upload_images/1084915-b5f77f1a19fc6e78.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 访问EOS浏览器查看

![image.png](https://upload-images.jianshu.io/upload_images/1084915-bc59dc81b6457260.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

可以注意到， 这个账号的owner 的密钥，跟active权限的密钥，是设置了不同的。


至于如何修改账号的权限，可以参考一下对应钱包的介绍。
比如，MeetOne有写了一篇文章，介绍如何修改：
[修改 Active/Owner Key](https://mp.weixin.qq.com/s/Cgee86tRkxl8KmNVs7naOA)


## EOS42 开创去中心化的未来

EOS42的账号为: eos42freedom。
请为EOS42投票，支持我们继续不停开拓去中心化解决方案的未来。

![vote for EOS42](https://upload-images.jianshu.io/upload_images/1084915-6ed2991946eccf72.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
