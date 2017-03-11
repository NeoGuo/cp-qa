# CP方需要提供的相关文件说明

1. (如果有内支付)请贵方提供内支付配置表，包括内购类型，名称，商品ID，价格等级，描述等等，以及内购的游戏界面截图(必须，苹果审核要看)。内支付的测试沙箱账号，由我方提供。

2. 贵方需要提供游戏的ICON(1024*1024，无透明通道)一张。产品宣传图两套(iPhone,iPad)，每套5张（尺寸：1242x2208、2048x2732）,分成ipad，iphone两个文件夹，每套宣传图标好数字号1.2.3.4.5，如有问题方便沟通。

3. ICON可以增加一些角标，比如hot、3D、PK之类的使ICON更突出

 ![image](http://tools.asostar.com/assets/img/Picture1.png)

4. 宣传图第1，2张，最佳效果为一个整体拼合效果。

 ![image](http://tools.asostar.com/assets/img/Picture2.png)

5. 需要提供游戏的简介

6. 如果游戏需要用户注册，需要提供测试账号(供苹果审核)

7. **2017月1月1日，苹果必须要求使用https协议。确保您的服务器链接遵循了这个规定。**

8. 如果有第三方支付，需要遵循下文中关于第三方支付的原则性约定。


# Q/A

### 合作的流程是怎样的？

答：我们只做苹果APP STORE正版发行。您需要提供IPA文件，及其他素材和说明，不需要提供开发者账号。

### 如何使用证书文件来打包IPA?

答：我们不提供开发者账号和密码，但会提供打包所需的证书。如果使用XCode打包，需要做一下设置：

* 取消Automatically manage signing
* 将p12和pp文件安装到电脑
* Code Signing 选择安装的证书
* Provisioning Profile选择安装的PP文件

### 会提供哪些证书？Bundle ID是谁提供？

答：证书根据您的需要来给出。您需要明确提供您需要的证书种类（测试证书，正式证书，推送证书）。如果需要测试证书，还需要提供您的测试设备的UUID。

Bundle ID和AppStore ID由我方提供，和证书一起提供给贵方。

### 关于IPV6的问题，是不是一定要支持IPV6？

自2016年6月份之后, Apple需要所有上架的APP适配Ipv6网的环境! 就是说，如果您没有针对IPV6环境做过测试，那很有可能被苹果拒绝。我们这边已经出现很多因为IPV6环境测试通不过被拒的案例了。

可以参考这篇网文写的解决方案：

[IOS 因为ipv6被拒问题解决方案](http://blog.csdn.net/lk623177086/article/details/52273863)

### 苹果支付

对接开始，我们要先约定好关于游戏商品支付的方式。如果要加第三方支付，参考下一条说明；如果只有苹果内购，那么只可以使用原生方式实现，**不允许使用任何形式的包含第三方支付功能的支付SDK**。

### 关于第三方支付的原则性约定

目前苹果对于第三方支付的审核非常严格，一旦发现，惩罚会非常重，不仅仅是下架APP，整个账号都会被封杀。所以我们总结经验教训，制定了关于第三方支付的原则性约定，合作方请仔细阅读，并遵守本约定。

如果要配置第三方支付，那么您可以选择如下两种方式中的一种：

1. 不在苹果后台配置内购商品，只在APP中对接第三方支付，审核的时候，关掉第三方支付，这样对苹果而言这是一个免费应用，是安全的。上线后，再把第三方支付打开。
2. 如果配置了苹果内购，那么上线之后，**绝对不可以屏蔽苹果内购**，必须保证第三方和苹果内购都是打开的。这是为了保证苹果有收入，降低被查水表的风险。

如果使用我方的支付SDK，是不允许在代码中再包含其它支付SDK的，要清理干净，一旦发现，终止合作。

> 需要尽量使用我方的支付SDK，现在苹果会扫描代码，其它支付容易被扫到有隐藏的第三方支付。

### 预防相似应用

苹果近期加大了对"马甲包"的打击力度，一旦发现，就会给严重警告，被发现第二次就会封账号。这种打击力度是空前的，所以我们不能低估苹果的决心。要防止这种情况，需要从下面几个方向入手：

1. **项目目录结构变化** 目录名称改一改，层级换一换，从结构上和原版的区别越大越好。
2. **代码混淆或手动更改类名称** 和上一条的作用相同，尽量和原有文件区分开，改改名，改改代码结构，也可以借助工具对代码进行一些随机混淆(不影响功能的前提下)。
3. **UI界面变化** 这一点也很重要，特别是审核人员容易看到的界面(加载，启动，人物形象，地图等等)，尽量重新设计。
4. **图标和宣传图** 每一个马甲包的图标和宣传图一定要重新设计，不能重复。

### 热更机制合法化

因为苹果的政策是不允许APP进行热更新的，但之前尺度比较松，所以也都相安无事。但最近热更新也是被严打的对象了。

参考文章：

[AppStore热更新被禁 对游戏有着怎样影响](http://www.72g.com/news/165444.html)

[苹果向热更新下达最后通牒 是什么导致了此事？](http://tech.163.com/17/0309/13/CF3EPTS900097U7R.html)

解决方案目前主要是两点：

1. 国内 App 如果有在使用 JSPatch 的，那么请移除；
2. 更新或者移除一些第三方使用 JSPatch 的 SDK。