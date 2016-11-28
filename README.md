# CP方需要提供的相关文件说明

1. (如果有内支付)请贵方提供内支付配置表，包括内购类型，名称，商品ID，价格等级，描述等等，以及内购的游戏界面截图(必须，苹果审核要看)。内支付的测试沙箱账号，由我方提供。

2. 贵方需要提供游戏的ICON(1024*1024，无透明通道)一张。产品宣传图两套(iPhone,iPad)，每套5张（尺寸：1242x2208、2048x2732）,分成ipad，iphone两个文件夹，每套宣传图标好数字号1.2.3.4.5，如有问题方便沟通。

3. ICON可以增加一些角标，比如hot、3D、PK之类的使ICON更突出

 ![image](https://github.com/NeoGuo/cp-qa/raw/master/images/Picture1.png)

4. 宣传图两张最好是拼接的效果图

 ![image](https://github.com/NeoGuo/cp-qa/raw/master/images/Picture2.png)

5. 需要提供游戏的简介

6. 如果游戏需要用户注册，需要提供测试账号(供苹果审核)

7. 2017月1月1日，苹果必须要求使用https协议。确保您的服务器链接遵循了这个规定。


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

http://blog.csdn.net/lk623177086/article/details/52273863
