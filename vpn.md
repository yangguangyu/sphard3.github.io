# 自建 VPN 翻墙
<iframe width="100%" height="315" src="https://www.youtube.com/embed/PdAYlMIyICk" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<br>
如果你没有办法点开上面的YouTube视频，可以点下面的哔哩哔哩视频链接
https://www.bilibili.com/video/av18733432/

本教程是以 Ubuntu server 为例子，如果你用的是其他系统，请使用对应的安装软件的命令<br>
如果你使用的不是 root 账号，那么在安装软件的时候可能会出现权限不够，可以通过 sudo 来增加权限解决问题
# 安装pptpd 
```
apt-get install pptpd
```

# 修改文件 /etc/pptpd.conf 
```
vi /etc/pptpd.conf 
```
找到 `# TAG: localip` 一行，在后面添加以下2行
``` 
localip 192.168.0.1 
remoteip 192.168.0.234-238,192.168.0.245
```

# 修改文件 /etc/ppp/pptpd-options 
```
vi /etc/ppp/pptpd-options
```
找到 `#ms-dns` 这行，去掉前面的#号，修改成 Google 提供的 DNS server 或其他 DNS
```
ms-dns 8.8.8.8 
ms-dns 8.8.4.4
```

# 修改文件 /etc/ppp/chap-secrets
```
vi /etc/ppp/chap-secrets
```
按一行四列添加账号、服务器名、密码和IP限制。服务器名（默认 写 pptpd 即可，务必与 pptpd-options 文件的 name 一行一样）<br>
如: 创建一个名为 `user`，密码为 `userpasswd` ，不限制登录 IP 的 VPN 账号
``` 
user pptpd userpasswd *
```

# 修改文件 /etc/sysctl.conf
```
vi /etc/sysctl.conf
```
找到 #net.ipv4.ip_forward=1 这一行，删掉 # 号，开启 ipv4 forward
```
sysctl -p
```
运行后会显示 net.ipv4.ip_forward = 1，就表示修改生效了

# 安装 iptables
```
apt-get install iptables
```
执行下面这条命令前先用 `ifconfig` 查看一下自己系统的网卡名, 如果网卡名是 `eth0` 就可以直接执行下面这条命令，如果不是，就请把下面命令里的 `eth0` 换成你自己的网卡名
```
iptables -t nat -A POSTROUTING -s 192.168.0.0/24 -o eth0 -j MASQUERADE
```
上面的24表示子网掩码，代表24个1

# 完成
不放心的话可以重启 server，或者重启 pptpd 
```
/etc/init.d/pptpd restart
```