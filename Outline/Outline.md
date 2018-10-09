# 搭建Outline翻墙
<iframe width="100%" height="415" src="https://www.youtube.com/embed/HYp759SJIKI" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<iframe src="//player.bilibili.com/player.html?aid=22229396&cid=36782522&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" width="100%" height="500"> </iframe>

[Outline](https://getoutline.org/en/home)官网：[https://getoutline.org/en/home](https://getoutline.org/en/home)

[Jigsaw](https://jigsaw.google.com)在[GitHub](https://github.com)上的官网：[https://github.com/Jigsaw-Code](https://github.com/Jigsaw-Code)

[Outline](https://getoutline.org/en/home)是一款基于ss的开源软件，来自于[Jigsaw](https://jigsaw.google.com)公司，致力于网络数据传输安全，并且号称不需要技术人员就能完成部署。

[Jigsaw](https://jigsaw.google.com)前身为Google Ideas，是Google旗下的技术孵化器公司，目标是以技术来克服全球的网络安全难题，包括地址网络审查制度、降低网络攻击的威胁，以及防止大众收到网络骚扰等。[Outline](https://getoutline.org/en/home)即为[Jigsaw](https://jigsaw.google.com)的成果之一。

服务器上使用的代码：
```bash
curl -sS https://get.docker.com/ | sh
systemctl start docker
systemctl enable docker
systemctl status docker
wget -qO- https://raw.githubusercontent.com/Jigsaw-Code/outline-server/master/src/server_manager/install_scripts/install_server.sh | bash
```
在电脑上下载安装 Outline 管理端
![](https://user-images.githubusercontent.com/34980980/38570402-56fcdae4-3d20-11e8-9f86-580c34adc83d.png)

然后在想要使用的平台上下载相应的客户端
![](https://user-images.githubusercontent.com/34980980/38570513-9b6ec7fa-3d20-11e8-9018-dfea764e36a9.png)
<a href="https://www.vultr.com/?ref=7295225"><img src="https://www.vultr.com/media/banner_1.png" width="100%" height="90"></a>