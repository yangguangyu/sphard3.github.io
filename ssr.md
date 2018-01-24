# 自建 ssr 翻墙

<iframe width="560" height="315" src="https://www.youtube.com/embed/_6lRX9S4knI" frameborder="0" gesture="media" allow="encrypted-media" allowfullscreen></iframe>
<br>
如果你没有办法点开上面的YouTube视频，可以点下面的哔哩哔哩视频链接
http://www.bilibili.com/video/av17968174/

# 购买VPS服务器
VPS服务器需要选择国外的，首选国际知名的 [Vultr](https://www.vultr.com/?ref=7295225)，速度不错、稳定且性价比高。<br>
使用下面的注册地址可以获得 **10美元的代金卷**<br>
[Vultr](https://www.vultr.com/?ref=7295225)注册地址：**https://www.vultr.com/?ref=7295225**

![](https://www.vultr.com/media/banner_1.png 'Vultr')

注册并邮件激活账号，充值后即可购买服务器。充值方式是PayPal或支付宝

[Vultr](https://www.vultr.com/?ref=7295225)实际上是折算成小时来计费的，比如服务器是5美元1个月，那么每小时收费为5/30/24=0.0069美元 会自动从账号中扣费，只要保证账号有钱即可。如果你部署的服务器实测后速度不理想，你可以把它删掉（destroy），重新换个地区的服务器来部署，因为新的服务器就是新的ip，所以当ip被墙时这个方法很有用。

计费从你开通服务器开始算的，不管你有没有使用，即使服务器处于关机状态仍然会计费，如果你没有开通服务器就不算。比如你今天早上开通了服务器，但你有事情，晚上才部署，那么这段时间是会计费的。同理，如果你早上删掉服务器，第二天才开通新的服务器，那么这段时间是不会计费的。

温馨提醒：同样的服务器位置，不同的宽带类型和地区所搭建的账号的翻墙速度会不同，以实测为准。

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
购买服务器后，需要部署一下。因为你买的是虚拟东西，而且又远在国外，我们需要一个叫 Git Bash 的软件来远程部署。<br>
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
如上图出现管理界面后，**输入数字1来安装SSR服务端。**

如果输入1后不能进入下一步，那么请重新连接VPS服务器，然后输入快捷管理命令 bash ssr.sh 再尝试

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
Windows SSR客户端  [点击下载地址](https://github.com/shadowsocksr-backup/shadowsocksr-csharp/releases '下载地址')<br>
MacOS SSR客户端  [点击下载地址](https://github.com/shadowsocksr-backup/ShadowsocksX-NG/releases '下载地址')<br>
Linux SSR客户端  [点击下载地址](https://github.com/erguotou520/electron-ssr/releases '下载地址')<br>
安卓 SSR客户端  [点击下载地址](https://github.com/shadowsocksr-backup/shadowsocksr-android/releases/download/3.4.0.8/shadowsocksr-release.apk '下载地址')<br>

苹果手机SSR客户端：Potatso Lite、shadowrocket都可以作为SSR客户端，但是，如果你配置的SSR账号兼容SS客户端，或者协议选择origin且混淆选择plain，那么你可以选择苹果SS客户端软件（即协议和混淆可以不填），APP商店里面有很多，比如：openwingy、superwingy、bestwingy等。

有了账号后，打开SSR客户端，填上信息，这里以Windows版的SSR客户端为例子：
![ssr13](https://i.imgur.com/LA81WuS.png)

在对应的位置，填上服务器IP、服务器端口、密码、加密方式、协议和混淆，最后点击确认

**现在你就可以愉快地科学上网了**