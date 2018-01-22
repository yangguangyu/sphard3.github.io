# 自建 ssr 翻墙

<iframe width="560" height="315" src="https://www.youtube.com/embed/_6lRX9S4knI" frameborder="0" gesture="media" allow="encrypted-media" allowfullscreen></iframe>
<br>
如果你没有办法点开上面的YouTube视频，可以点下面的哔哩哔哩视频链接
http://www.bilibili.com/video/av17968174/

# 购买VPS服务器
VPS服务器需要选择国外的，首选国际知名的vultr，速度不错、稳定且性价比高。
使用下面的注册地址可以获得 **10美元的代金卷**
vultr注册地址：**https://www.vultr.com/?ref=7295225**

![](https://www.vultr.com/media/banner_1.png 'vultr')

虽然是英文界面，但是现在的浏览器都有网页翻译功能，鼠标点击右键，选择网页翻译即可翻译成中文。
注册并邮件激活账号，充值后即可购买服务器。充值方式是PayPal或支付宝

2.5美元/月的服务器配置信息：单核 512M内存 20G SSD硬盘 100M带宽 500G流量/月

5美元/月的服务器配置信息：单核 1G内存 25G SSD硬盘 100M带宽 1000G流量/月

10美元/月的服务器配置信息：单核 2G内存 40G SSD硬盘 100M带宽 2000G流量/月

20美元/月的服务器配置信息：2cpu 4G内存 60G SSD硬盘 100M带宽 3000G流量/月

40美元/月的服务器配置信息：4cpu 8G内存 100G SSD硬盘 100M带宽 4000G流量/月

vultr实际上是折算成小时来计费的，比如服务器是5美元1个月，那么每小时收费为5/30/24=0.0069美元 会自动从账号中扣费，只要保证账号有钱即可。如果你部署的服务器实测后速度不理想，你可以把它删掉（destroy），重新换个地区的服务器来部署，因为新的服务器就是新的ip，所以当ip被墙时这个方法很有用。

计费从你开通服务器开始算的，不管你有没有使用，即使服务器处于关机状态仍然会计费，如果你没有开通服务器就不算。比如你今天早上开通了服务器，但你有事情，晚上才部署，那么这段时间是会计费的。同理，如果你早上删掉服务器，第二天才开通新的服务器，那么这段时间是不会计费的。

温馨提醒：同样的服务器位置，不同的宽带类型和地区所搭建的账号的翻墙速度会不同，以实测为准。

购买vps服务器时，不推荐首选洛杉矶和日本位置的服务器，因为这两个位置的服务器前期被很多大陆同胞疯狂追捧，导致现在一开洛杉矶或日本服务器就会遇到被墙的ip，开到能联通的ip概率很小。

下面是图片演示步骤：
![1](https://i.imgur.com/QuQEHCn.png)
![2](https://i.imgur.com/G4UGPSl.png)
![3](https://i.imgur.com/dZl1mWK.png)
![4](https://i.imgur.com/FkC49xK.png)
![5](https://i.imgur.com/RTtSZGe.png)
![6](https://i.imgur.com/2CT7SSi.png)
![7](https://i.imgur.com/JIB0X1L.png)
![8](https://i.imgur.com/zAUdJFz.png)
![9](https://i.imgur.com/2MJsM0I.png)

# 部署VPS服务器
Windows用户请看：
购买服务器后，需要部署一下。因为你买的是虚拟东西，而且又远在国外，我们需要一个叫 Git Bash 的软件来远程部署。
官方免费下载地址：https://git-scm.com/downloads
![git bash](https://i.imgur.com/TM8SCDQ.png)
如果你是Linux或者MacOS用户，请忽略上面的软件
直接打开终端（Terminal），输入 ssh root@ip 其中“ip”替换成你 VPS 的 IPv4 地址, 按回车键，然后复制粘贴密码，按回车键即可登录。粘贴密码时不显示密码，但不影响。
在开始登陆服务器之前，我们先打开命令行ping一下自己服务器上的IP地址是否能ping通
<br>
![ping](https://i.imgur.com/iyW35ax.png)
接着打开 git bash 软件，输入 `ssh root@你的服务器ip地址`
<br>
![ssh1](https://i.imgur.com/vMcpXwZ.png)
<br>
出现下面这张图，就说明你已经成功登陆你的服务器了！
<br>
![ssh2](https://i.imgur.com/0MZFmji.png)

# 安装ssr软件
```
wget -N --no-check-certificate https://softs.fun/Bash/ssr.sh && chmod +x ssr.sh && bash ssr.sh
```
![ssh3](https://i.imgur.com/y4cj0rr.png)
复制上面的代码到VPS服务器里，安装脚本后，以后只需要运行`bash ssr.sh`这个快捷命令就可以出现下图的界面进行设置管理了
<br>
![ssr1](https://i.imgur.com/rxKvBqU.png)
<br>
如上图出现管理界面后，**输入数字1来安装SSR服务端。**如果输入1后不能进入下一步，那么请重新连接VPS服务器，然后输入快捷管理命令 bash ssr.sh 再尝试
选择端口直接回车选择默认的就好了。当然了，你也可以设置其他的端口，这个根据个人需求
<br>
![ssr2](https://i.imgur.com/mimLhWy.png)
<br>
然后设置密码，选择加密方式
![ssr3](https://i.imgur.com/EY98FzT.png)
<br>
接下来选择协议插件
<br>
![ssr4](https://i.imgur.com/GKob99t.png)
<br>
再然后根据自己需求选择是否兼容原版ss客户端
<br>
![ssr5](https://i.imgur.com/1K3IrbA.png)
<br>
之后选择混淆插件
<br>
![ssr6](https://i.imgur.com/4cNQiwg.png)
进行混淆插件的设置后，会依次提示你对设备数、单线程限速和端口总限速进行设置，默认值是不进行限制，个人使用的话，选择默认即可，一路敲回车键。
![ssr7](https://i.imgur.com/Utz2lNU.png)
耐心等待一会，出现下面的界面即部署完成：
![ssr8](https://i.imgur.com/tNuZx6q.png)
输入快捷管理命令：`bash ssr.sh` 进入管理界面
![ssr9](https://i.imgur.com/2eOXkOw.png)
<br>
根据上图就可以看到自己设置的ssr账号信息，包括IP、端口、密码、加密方式、协议插件、混淆插件等等，如果之后想修改账号信息，选择相应的数字来进行一键修改

# 加速VPS服务器 (谷歌BBR加速)
```
wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh

chmod +x bbr.sh

./bbr.sh
```
执行上面的代码，然后耐心等待，安装成功后重启VPS服务器即可
![ssr10](https://i.imgur.com/NcOiqdD.png)
![ssr11](https://i.imgur.com/FeuTxoN.png)
![ssr12](https://i.imgur.com/zNhE3Vs.png)
<br>
最后重启服务器

# ssr客户端下载
Windows SSR客户端  [点击下载地址](https://github.com/shadowsocksr-backup/shadowsocksr-csharp/releases '下载地址')
MacOS SSR客户端  [点击下载地址](https://github.com/shadowsocksr-backup/ShadowsocksX-NG/releases '下载地址')
Linux SSR客户端  [点击下载地址](https://github.com/erguotou520/electron-ssr/releases '下载地址')
安卓 SSR客户端  [点击下载地址](https://github.com/shadowsocksr-backup/shadowsocksr-android/releases/download/3.4.0.8/shadowsocksr-release.apk '下载地址')

苹果手机SSR客户端：Potatso Lite、Potatso、shadowrocket都可以作为SSR客户端，但这些软件目前已经在国内的app商店下架，可以用美区的appid账号来下载。但是，如果你配置的SSR账号兼容SS客户端，或者协议选择origin且混淆选择plain，那么你可以选择苹果SS客户端软件（即协议和混淆可以不填），APP商店里面有很多，比如：openwingy、superwingy、bestwingy、wingy+、greatwingy等。

有了账号后，打开SSR客户端，填上信息，这里以Windows版的SSR客户端为例子：
![ssr13](https://i.imgur.com/LA81WuS.png)

在对应的位置，填上服务器IP、服务器端口、密码、加密方式、协议和混淆，最后点击确认<br>
**现在你就可以愉快地科学上网了**

# 常见问题解决方法

1、用了一段时间发现SSR账号用不了了？

多半是被墙了，即ip失效。首先ping一下自己的ip，看看能不能ping的通，ping不通那么就是ip被墙了，遇到这种情况重新部署一个新的服务器，新的服务器就是新的ip。关于怎么ping ip的方法，可以自行网上搜索，很简单。vultr服务商是折算成小时计费，且开通和删除服务器非常方便（新服务器即新ip。大多数vps服务商都没有这样的服务，一般的vps服务商可能会提供更换1次ip的服务，如果你买的是别家的vps，一定要了解是否能够更换ip，假如不能，那么万一你的ip不幸被墙，钱就打水漂了）

2、刚搭建好的ssr账号，ip能ping通，但是还是用不了？

首选排除杀毒软件的干扰，尤其是国产杀毒软件，比如360安全卫生、360杀毒软件、腾讯管家、金山卫士等。这些东西很容易干扰翻墙上网，如果你的电脑安装了这样的东西，建议至少翻墙时别用。其次，检查下SSR信息是否填写正确。浏览器的代理方式是否是ssr代理，即127.0.0.1 1080端口。如果以上条件都排除，还是用不了，那么可以更换端口、加密方式、协议、混淆，或者更换服务器位置

3、vultr服务商提供的 VPS 服务器是单向流量计算，有的vps服务商是双向流量计算，单向流量计算对于用户来说更实惠。因为我们是在 VPS 服务器上部署SSR服务端后，再用SSR客户端翻墙，所以SSR服务端就相当于中转，比如我们看一个视频，必然会产生流量，假如消耗流量80M，那么VPS服务器会产生上传80M和下载80M流量，vultr服务商只计算单向的80M流量。如果是双向计算流量，那么会计算为160M流量

4、如果你想把搭建的账号给多人使用，不用额外设置端口，因为一个账号就可以多人使用