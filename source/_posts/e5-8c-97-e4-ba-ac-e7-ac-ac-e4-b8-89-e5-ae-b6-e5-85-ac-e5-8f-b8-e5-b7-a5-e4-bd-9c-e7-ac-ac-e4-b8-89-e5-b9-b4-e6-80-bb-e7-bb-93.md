---
title: 我的程序员之路（10）——北京第三家公司工作第三年总结
categories:
  - 我的程序员之路
date: 2016-01-05 21:32:11
tags:
---

转眼2016年1月5号，在这家公司工作整整三年了。工作主要内容如下：

1、新开发了视频广告SDK。

视频使用MPMoviePlayerController播放，需要另外加其他视图如控制按钮，所以直接取出其view加到自己的view（UIViewController的view）上。视频文件下载使用自己实现的文件分段下载方案（由于要兼容iOS6，所以未使用NSURLSession），后来改用自己写的[AFNetworking精简版SimplifiedAFN（iOS7以下使用NSURLConnection进行分段下载，iOS7及以上使用NSURLSession的下载。如果app不支持iOS7以下系统，则自动屏蔽NSURLConnection方案不参与编译）](https://github.com/yjh4866/SimplifiedAFN)。

2、新开发非下载类积分墙。

由于苹果打击奖励下载app类的积分墙，所以开发了非下载类的积分墙。基本上没有版本迭代。

3、广告SDK升级。

由于好多开发者只使用Banner和插屏，不需要推荐墙，所以增加了一个Lite版本的Target（苹果后来也打击推荐墙，所以被拒的开发者直接用Lite版，不需要另外发版本了）。脚本打包时适配了Xcode7的BitCode。不再支持iOS5以下系统，所以JSON解析没必要使用JSONKit，直接用苹果自带的JSON解析了，尽量减小包大小。网络请求支持NSURLSession，等最新的视频广告SDK发布后，将视频广告合入广告SDK，网络请求改用[SimplifiedAFN](https://github.com/yjh4866/SimplifiedAFN)。还有一些大开发者的专用包，头文件也与普通包不一样，只好专门创建Target。

4、聚合SDK。只是基本架构出来了，没有正式发布。

5、集合SDK。

由于要开发一些app用于协助播放Web推荐墙上的视频广告，而这些app有很多一样的功能，如推送、分享、广告等，所以将这些SDK及功能合成一个SDK以备更多的app使用。

6、猎豹浏览器、上网导航等协助播放视频广告的app。

这俩app的名字不错吧。猎豹浏览器被苹果下架了，说是误导用户。

7、天天跑酷。

源码是Android版本的，coco2d-x 2.x版本实现的，适配了一下iOS平台，增加了一些IAP。不过没通过审核，说是跟《天天酷跑》太像。

8、XXXX、XXXX

俩人开发了俩app，这是后半年的主要工作。app开发没什么技术含量，要说学到的，一是使用了传说中的AFNetworking，看源码学会了些GCD，后来自己实现了[精简版SimplifiedAFN](https://github.com/yjh4866/SimplifiedAFN)。二是终于接受ARC了，之前一直不愿意用ARC，为此甚至跟人吵架，看到weak的特性后，我真想把之前所有工程都改成ARC的。

9、维护一款Unity的游戏，接入芒果聚合广告。我的游戏也因此接入了芒果聚合。

10、XXXXSDK。

一款app，有网页版的，专门做成SDK以便在其他app中使用。

&nbsp;

&nbsp;

自己学习方面嘛，

1、年初上架了一款Unity游戏。年末赶在圣诞前又上架一款Unity游戏，这个游戏的图标是找专业UI做的。

2、上架了两款2dx实现的游戏。其中一款是剪刀石头布玩法的。另一款是俄罗斯方块，有人机对战玩法（五月份在cocos平台上分享了一下AI算法，因分享数和阅读量，还获得了机械键盘），几经周折终于最终上架了，不明白的是，为什么上了好几款叫俄罗斯方块的游戏，我的游戏就是不能叫俄罗斯方块。

3、准备用Cocos Studio升级一款游戏，是我在AppStore发布的第一款游戏。目前大约实现了三分之一。

4、几款app版本升级。

5、[AFNetWorking精简版](https://github.com/yjh4866/SimplifiedAFN)。

比AFNetworking有很大优点。文件下载方面iOS7以下使用NSURLConnection进行分段下载，iOS7及以上使用NSURLSession的下载。更好的是如果app不支持iOS7以下系统，则自动屏蔽NSURLConnection方案不参与编译。而AFNetwoking则是分成NSURLConnection方案和NSURLSession方案两部分，而且好几个类，肯定不适合在SDK开发中使用。

过去的一年学到的也不少。新的一年注意以下方面：

1、继续熟悉GCD

2、尽可能学Swift

3、重写《新浪博客阅读器》（即新浪博客客户端的个人版》，并在Github上分享

4、尽量多学点Unity用以实现更好玩更漂亮的游戏，也好多赚小钱钱呀

5、尽可能提高表达能力，得多关注技术的描述而不止是技术本身