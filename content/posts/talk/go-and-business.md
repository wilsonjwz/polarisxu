---
title: "聊聊 Go 和创业"
date: 2020-11-18T18:40:00+08:00
toc: true
isCJKLanguage: true
tags: 
  - Go
  - TiDB
---

昨天 PingCAP 完成 D 轮 2.7 亿美元融资的消息，相信很多人看到了。PingCAP 今天的成就，对开源界真是极大的鼓舞。祝贺祝贺！

## 01

PingCAP 成立于 2015 年，是一家企业级开源分布式数据库厂商，提供包括开源分布式数据库产品、解决方案与咨询、技术支持与培训认证服务，致力于为全球行业用户提供稳定高效、安全可靠、开放兼容的新型数据基础设施，解放企业生产力，加速企业数字化转型升级。

由 PingCAP 创立的分布式关系型数据库 TiDB，为企业关键业务打造，具备「分布式强一致性事务、在线弹性水平扩展、故障自恢复的高可用、跨数据中心多活」等企业级核心特性，帮助企业最大化发挥数据价值，充分释放企业增长空间。

对 TiDB 有所耳闻的都知道，它是使用 Go 语言实现的，它的创始人兼 CEO 刘奇早期就活跃在 Go 社区，早在豌豆荚，他就主导开源了 [Codis](https://github.com/CodisLabs/codis)。

PingCAP 的员工，一直活跃在各大社区，包括频频出席各种技术交流、分享场所，他们创业早期，刘奇本人都经常分享 TiDB。5 年的时间，做出这样的成绩，真的是开源界特别值得骄傲的事情。这样纯技术驱动的公司，是不是每个技术人员向往的呢？！

## 02

另一个创业公司，也是和 Go 有关：七牛。相信 Go 圈内知道的更多。我个人的看法，七牛和 Go 是相互成就的。

七牛成立于 2011 年 6 月，那时候 Go1.0 还未发布（Go1.0 是 2012 年 3 月 28 日发布的）。七牛的创始人兼 CEO 许式伟离开盛大创新院创办七牛云时，面临技术选型。尽管 Go 正式版本都还未发布，但他很坚决地选择了 Go 语言。为此他还专门给团队发了一封邮件，邮件中有一段是这么说的：

> 在创业过程中我们会面临很多选择，也会有很多选择后来会被证明是错的，但是今天我可以确定的是，选择 Go 将会成为我们最正确的选择。

在选择了 Go 语言后，考虑到 Go 仍然是一门十分小众的语言，七牛开始有意识地培养 Go 中国社区。为了让更多人能够知道 Go，加入 Go 的行列，他们做了很多工作，比如启动了《Go 语言编程》一书的编写工作，并最终和 Go 1.0 版本同步发布。2012 年 2 月，许老板首次在公开场合说：Go 会超过 C、Java，成为最流行的语言。这一年他到处宣讲，做了不下十场的 Go 语言讲座，平均每个月有一场。讲得最多的一个 PPT 是《Go，Next C》这篇，它基本上算他对 Go 的革命性到底在哪里的一个总结。对于一个初创公司来说，为一个并不属于自己业务的技术这么花时间去宣传，有些人可能会觉得比较不可理解。但是实际上有三个理由支撑他们这么做：

- Go 真的是一门革命性的语言，它的流行将对产业发展具重大意义。
- Go 仍然是一门小众语言，而我们不止要招 Go 程序员，更重要的是要说服他们相信 Go 语言是有远大前景的专业技能方向。
- 七牛的用户是程序员，我们需要建立在用户心目中的专家形象。

大家看到了现在 Go 语言的发展势头，同时作为一个创业公司，七牛云今年 6 月份获得了 F 轮 10 亿人民币的融资。

七牛为 Go 的发展做了很大的贡献，另一方面，我认为，正是因为借助 Go，也让七牛发展的更好。

## 03

再聊一个和 Go 没啥关系的公司，但相信大家都知晓。

掘金社区，大家不陌生。号称是一个帮助开发者成长的社区，是给开发者用的 Hacker News，给设计师用的 Designer News，和给产品经理用的 Medium。

2015 年阴明（网名 kalasoo） 创办了稀土掘金公司（2014 年底获得天使轮融资），运营掘金社区网站，16 年初获得 Pre-A 轮融资，17 年中旬获得 A 轮融资。之后并没有获得融资，运营很艰难。我记得去年，阴明大佬还做了一次女装直播，还发了文章，据说公司没有开发人员了，自己得学全栈技术，维护网站的运营，感觉随时有倒闭的风险。

今年 8 月份，听字节跳动的朋友说，在公司内部发现了掘金这个部门，而且在内部可以搜到掘金创始人和站长。前段时间，也证实了字节跳动收购了掘金。具体见：<https://xw.qq.com/cmsid/20201104A04LTM00>。

被收购，对掘金来说，也许是一个不错的出路。

## 04

常说创业九死一生，而我自己也一直在创业中（并非 Go 语言中文网），个中滋味只有自己清楚。作为技术人员，PingCAP、七牛 这样技术驱动的公司是很向往的，但自己作为创始人是很难的。

掘金，外面看来，网站做的很不错，但一直却活得很辛苦。我个人也运营了一个网站，投入的时间和心血，只有我自己知晓，它一直还只是我的个人项目，也许一直会是我的个人爱好项目。当时听到掘金被并购的消息，同样作为网站创建者，感触颇多，如果有资本的进入，也许就不能只是爱好了。。。

## 参考资料

<https://www.sohu.com/a/197332119_355140>