# 连接服务器常见问题
<iframe width="100%" height="315" src="https://www.youtube.com/embed/mm08uNWo7qA" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
如果你没有办法点开上面的YouTube视频，可以点下面的哔哩哔哩视频链接<br>
`B站视频正在审核中。。。。。。`

![vps](https://i.imgur.com/RLJX1HE.png)

### 遇到上图问题的解决办法是：<br>

![vps](https://i.imgur.com/TUn4gKG.png)

1、用文本编辑器打开 `/c/Users/darren/.ssh/known_hosts` 这个文件（注意：`daren`是我的用户名，你的用户名可能是其他名字）

2、删除 `/c/Users/darren/.ssh/known_hosts:31` 这一行（注意：我这边是31行，你那边不一定是31行）

3、（一定要注意：认认真真看清楚你自己那边的报错信息，每个人的用户名都不一样，不是每一个人的用户名都叫 `darren` 。每个人的 `known_hosts` 文件里的数据量都是不一样的，我这边是 31 行，你那边有可能是 20 行，也有可能是 1000 行，一定要认认真真看报错信息！）

<a href="https://www.vultr.com/?ref=7295225"><img src="https://www.vultr.com/media/banner_1.png" width="100%" height="90"></a>