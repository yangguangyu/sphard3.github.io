# 各种翻墙对比
### Shadowsocks作者是谁？是否还在更新？
Shadowsocks是由若干人因为兴趣而制作的一个项目，主要开发者和领导者是[@clowwindy](https://twitter.com/clowwindy) ，但是在2015年下半年被“相关部门”约谈喝茶，于是被迫删除[Github](https://github.com)的源码及相关文档。
![Shadowsocks](https://img.doub.pw/ss-jc35-1-01.png)

但Shadowsocks属于开源项目，所以删除前已经有人备份，同时由另一个志愿者跟进维护原版[Shadowsocks](https://github.com/shadowsocks/shadowsocks-windows/releases)客户端，而其他基于Shadowsocks项目的第三方项目有：[ShadowsocksR](https://github.com/shadowsocksr-backup/shadowsocksr)、[Shadowsocks-qt5](https://github.com/shadowsocks/shadowsocks-qt5)、[ShadowsocksCap](https://sourceforge.net/projects/sscap/)等来维护更新Window/Linux客户端（其他系统的不一一举例了）。

### Shadowsocks是否安全？加密性如何？
Shadowsocks是被设计来混淆数据，增加 墙 检查出流量特征所需的计算量，提高实时检测和匹配的成本，而不是加密。

SS的作者多次强调过这一点--->[Correct username/password auth model · Issue #169 · shadowsocks/shadowsocks · GitHub](https://github.com/shadowsocks/shadowsocks/issues/169)

> "We don't need security. We need indistinguishability from random bytes."










感谢参考：[逗比根据地-->关于Shadowsocks的小白常见问题 总结篇](https://doub.io/ss-jc35/)