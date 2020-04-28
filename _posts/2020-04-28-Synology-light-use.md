---
layout: post
title: 群辉轻度使用
tags: DSM synology 机器人兴趣小组 RoboMaster
comment: true
---

尽管去年11月战队就购买了一台DS218+，但并没有进行折腾。一来SMB本身似乎已经足够好用，再而并无折腾需求——大多数成员都7*24呆在局域网，似乎不需要增加其他折腾。最后，事实上我也没有时间过多折腾。

随后到来的疫情改变了需求——本来7日假期用DSM便可撑过去（~~事实上我也不会折腾~~），于是便找`t123yh`学长要了一些端口。愚笨的我当时连WebDAV都不知道。后来在`Evan-GH`大佬的友情提示下，配合Windows客户端（nautilus则直接支持dav://与davs://），达到了可以将就用的效果。但仍然是HTTP，并不能说安全。

在家闲置太久后，我终于开始打算折腾了。在`t123yh`学长的[支持](https://github.com/t123yh/lede-ddns-dnspod)下，配置了DDNS。HTTPS则使用了`acme.sh`。配置过程其实并没有想象的复杂至极。这时便有了`WebDAVS`和`HTTPS`，可以基本使用了。

![image-raidrive](/asset/images/2020-04/Synology-light-use/raidrive.png)

![image-explorer](/asset/images/2020-04/Synology-light-use/explorer.png)

于是我开始慢慢尝试它的其他功能。首先尝试了`Drive`。打开之后发现界面还挺像`seafile`的，功能也有相似之处——分享链接，多人协作，版本管理，自动备份等。

有些意思的是其内置的Office。其文档对`docx`支持并不是特别好，有些文档打开后会爆炸。不过其表格表现还行，~~目前正在以统计早餐的借口测试稳定性~~，多人的表现效果也不错。

愚笨的本人在配置的过程中还犯了愚蠢的错误，又没有认真读文档。家用宽带`DDNS`方式部署到公网一般是不能使用443端口，于是分享链接需要自定义一下。`外部访问`选项正确填写后，在Drive控制台中，应选择`外部IP`而非`自定义`。

![image-link](/asset/images/2020-04/Synology-light-use/link.png)

另外一个有趣的功能是`Virtual Machine Manager`，可以在群晖上部署虚拟机，并方便的分配访问权限。其连接速度还算不错，尽管感觉不如微软自家远程桌面快，但也仍可接受。通过网页连接也有HTTPS，有一定的安全保障。但鄙人手中的`DS218+``CPU`性能着实不佳，运行常规`Ubuntu1804`也能感受明显卡顿，大概还是只跑服务或者氪更多的金比较合适。

另外常见的——audio station，上传了歌曲后在app中感觉能用，但鄙人歌单较多，想到要重新找歌便不想尝试了。（~~实际感觉app并不是非常好用~~）

至于video station，鄙人有支持网络视频流的播放器，也下了`ds file`，并不想再下载一个app，于是也没有体验。

至于Moments，这是app里面我最感兴趣的一个了，但鄙人暂时不想将个人照片上传至公用设备。不过看Play商店的评价，感觉8太行。似乎离替代Google Photos还差得远。

正当我准备体验Git服务器，Mail Server等套件时，我们的`机器人兴趣小组`便开组了。于是我又没有时间体验了。

所以，有什么挣钱的办法吗？q(≧▽≦q)

