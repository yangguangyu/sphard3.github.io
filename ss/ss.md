# 搭建 Shadowsocks 科学上网 ss
<iframe width="100%" height="415" src="https://www.youtube.com/embed/LdrYnNCP-9w" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<iframe width="100%" height="500" src="//player.bilibili.com/player.html?aid=24249871&cid=40661718&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
Shadowsocks官网: [https://shadowsocks.org](https://shadowsocks.org)

Shadowsocks官方GitHub: [https://github.com/shadowsocks](https://github.com/shadowsocks)

服务器环境:<br>
系统: CentOS 6，7，Debian，Ubuntu<br>
内存: ≥128M

### 默认配置
<font color="red">服务器端口:</font> 自己设定（如不设定，默认从 9000-19999 之间随机生成）
<font color="red">密码:</font> 自己设定（如不设定，默认为 teddysun.com）
<font color="red">加密方式:</font> 自己设定（如不设定，默认为 aes-256-gcm）

### 安装ss
1. 使用 root 用户登录服务器, 运行以下命令
```bash
wget --no-check-certificate -O shadowsocks.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
```
```bash
chmod +x shadowsocks.sh
```
```bash
./shadowsocks.sh 2>&1 | tee shadowsocks.log
```

2. 安装完成示例<br>
![ss](https://i.imgur.com/wDFzpxn.png)

### 卸载ss
使用 root 用户登录服务器, 运行以下命令
```bash
./shadowsocks.sh uninstall
```

### ss使用命令
1. 启动: `/etc/init.d/shadowsocks start`
2. 停止: `/etc/init.d/shadowsocks stop`
3. 重启: `/etc/init.d/shadowsocks restart`
4. 状态: `/etc/init.d/shadowsocks status`

### 查看ss配置信息
使用 root 用户登录服务器, 运行以下命令
```bash
cat /etc/shadowsocks.json
```

### 修改ss配置信息
方法1: 修改文件`/etc/shadowsocks.json`<br>
方法2: 重新安装`./shadowsocks.sh`
<a href="https://www.vultr.com/?ref=7295225"><img src="https://www.vultr.com/media/banner_1.png" width="100%" height="90"></a>