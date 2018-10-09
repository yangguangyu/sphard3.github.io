# 搭建V2Ray翻墙
<iframe width="100%" height="415" src="https://www.youtube.com/embed/GV4VhUOc7hg" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<iframe src="//player.bilibili.com/player.html?aid=21240412&cid=34891307&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" width="100%" height="500"> </iframe>
V2Ray官网：[https://www.v2ray.com](https://www.v2ray.com)

白话文教程：[https://toutyrater.github.io](https://toutyrater.github.io)

## 时间校准
对于 V2Ray，它的验证方式包含时间，就算是配置没有任何问题，如果时间不正确，也无法连接 V2Ray 服务器的，服务器会认为你这是不合法的请求。所以系统时间一定要正确，只要保证时间误差在一分钟之内就没问题。

对于 VPS(Linux) 可以执行命令 date -R 查看时间：
```bash
$ date -R
Sun, 22 Jan 2017 10:10:36 -0500
```

## 修改上海时区
这里以修改上海时间作为默认时区，如果有其他需要的，可以对应修改
```bash
rm -rf /etc/localtime #先删除默认的时区设置
ln -s /usr/share/zoneinfo/Asia/Shanghai /etc/localtime #替换上海作为默认
```

## Linux 安装脚本
V2Ray 提供了一个在 Linux 中的自动化安装脚本。这个脚本会自动检测有没有安装过 V2Ray，如果没有，则进行完整的安装和配置；如果之前安装过 V2Ray，则只更新 V2Ray 二进制程序而不更新配置。

以下指令假设已在 su 环境下，如果不是，请先运行 sudo su。

运行下面的指令下载并安装 V2Ray。当 yum 或 apt-get 可用的情况下，此脚本会自动安装 unzip 和 daemon。这两个组件是安装 V2Ray 的必要组件。如果你使用的系统不支持 yum 或 apt-get，请自行安装 unzip 和 daemon
```bash
bash <(curl -L -s https://install.direct/go.sh)
```

此脚本会自动安装以下文件：
1. /usr/bin/v2ray/v2ray：V2Ray 程序；
2. /usr/bin/v2ray/v2ctl：V2Ray 工具；
3. /etc/v2ray/config.json：配置文件；
4. /usr/bin/v2ray/geoip.dat：IP 数据文件
5. /usr/bin/v2ray/geosite.dat：域名数据文件

此脚本会配置自动运行脚本。自动运行脚本会在系统重启之后，自动运行 V2Ray。

目前自动运行脚本只支持带有 Systemd 的系统，以及 Debian / Ubuntu 全系列。

运行脚本位于系统的以下位置：
1. /etc/systemd/system/v2ray.service: Systemd
2. /etc/init.d/v2ray: SysV

脚本运行完成后，你需要：
1. 编辑 /etc/v2ray/config.json 文件来配置你需要的代理方式；
2. 运行 service v2ray start 来启动 V2Ray 进程；
3. 之后可以使用 service v2ray start|stop|status|reload|restart|force-reload 控制 V2Ray 的运行。

## 服务器端配置
```bash
{
  "inbound": {
    "port": 10086, // 服务器监听端口，必须和上面的一样
    "protocol": "vmess",
    "settings": {
      "clients": [{ "id": "b831381d-6324-4d53-ad4f-8cda48b30811" }]
    }
  },
  "outbound": {
    "protocol": "freedom",
    "settings": {}
  }
}
```
服务器的配置中需要确保 id 和端口与客户端一致，就可以正常连接了。

## 客户端配置
在你的 PC （或手机）中，你需要运行 V2Ray 并使用下面的配置：
```bash
{
  "inbound": {
    "port": 1080,  // SOCKS 代理端口，在浏览器中需配置代理并指向这个端口
    "listen": "127.0.0.1",
    "protocol": "socks",
    "settings": {
      "udp": true
    }
  },
  "outbound": {
    "protocol": "vmess",
    "settings": {
      "vnext": [{
        "address": "server", // 服务器地址，请修改为你自己的服务器 ip 或域名
        "port": 10086,  // 服务器端口
        "users": [{ "id": "b831381d-6324-4d53-ad4f-8cda48b30811" }]
      }]
    }
  },
  "outboundDetour": [{
    "protocol": "freedom",
    "tag": "direct",
    "settings": {}
  }],
  "routing": {
    "strategy": "rules",
    "settings": {
      "domainStrategy": "IPOnDemand",
      "rules": [{
        "type": "field",
        "ip": [
          "0.0.0.0/8",
          "10.0.0.0/8",
          "100.64.0.0/10",
          "127.0.0.0/8",
          "169.254.0.0/16",
          "172.16.0.0/12",
          "192.0.0.0/24",
          "192.0.2.0/24",
          "192.168.0.0/16",
          "198.18.0.0/15",
          "198.51.100.0/24",
          "203.0.113.0/24",
          "::1/128",
          "fc00::/7",
          "fe80::/10"
        ],
        "outboundTag": "direct"
      }]
    }
  }
}
```
上述配置唯一要改的地方就是你的服务器 IP，配置中已注明。上述配置会把除了局域网（比如访问路由器）之外的所有流量转发到你的服务器。
<a href="https://www.vultr.com/?ref=7295225"><img src="https://www.vultr.com/media/banner_1.png" width="100%" height="90"></a>