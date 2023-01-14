# 安全 DIY 车库开门器

> 原文：<https://learn.sparkfun.com/tutorials/secure-diy-garage-door-opener>

## 介绍

如果你想增加你的车库门的安全性，或者你只是对学习更多的密码学感兴趣，那么继续读下去吧！这个项目的核心就是一个安全的无线按钮。这可以用来触发任何数量的事情，所以我们希望它可以激发未来许多其他项目的消息安全性。

[https://www.youtube.com/embed/S7GRFRJbG7M/?autohide=1&border=0&wmode=opaque&enablejsapi=1](https://www.youtube.com/embed/S7GRFRJbG7M/?autohide=1&border=0&wmode=opaque&enablejsapi=1)

*Project showcase video.*

我很惊讶地得知，即使你的车库门相当新，你仍然容易受到中间人或 T2 的攻击。通过本教程，您可以利用 ECC 签名和 [SparkFun 加密协处理器](https://www.sparkfun.com/products/15573)实现极高的安全性。

如果你想了解更多关于车库门的内容，这里有两篇关于黑客和历史的文章。

*   车库门黑客:怎么回事？

*   [车库门开启器(非常)短暂的历史](https://www.garageautomatics.com/garage-door-opener-history/)

在我为这个项目做研究的过程中，我还遇到了一个关于旧金山车库门的有趣故事。2004 年，军用无线电信号干扰了车库开门器。似乎当时大多数车库门开启器的工作频率与一个新的军事通信系统相同(390 MHz)。更多细节，请看这篇 [CBS 新闻文章](https://www.cbsnews.com/news/military-jams-garage-doors-openers/)。了解到这一点后，我很高兴知道我的新设置是在 915MHz 上运行的，所以它不会受到影响。

大部分沟通渠道都暴露在世界面前。无论是硬连线连接还是空中飞行的无线信号，任何人都可以监听并试图拦截、记录和/或模仿您的信号。那么我们如何保护自己免受这些恶意攻击呢？令人惊讶的是，您可以使用几个 Pro RFs 和我们的密码协处理器来创建一个非常健壮的解决方案。

### 推荐阅读

如果您不熟悉以下概念，我们建议您在继续之前通读这些教程。

[](https://learn.sparkfun.com/tutorials/serial-communication) [### 串行通信](https://learn.sparkfun.com/tutorials/serial-communication) Asynchronous serial communication concepts: packets, signal levels, baud rates, UARTs and more![Favorited Favorite](# "Add to favorites") 100[](https://learn.sparkfun.com/tutorials/i2c) [### I2C](https://learn.sparkfun.com/tutorials/i2c) An introduction to I2C, one of the main embedded communications protocols in use today.[Favorited Favorite](# "Add to favorites") 128[](https://learn.sparkfun.com/tutorials/sparkfun-samd21-pro-rf-hookup-guide) [### SparkFun SAMD21 Pro 射频连接指南](https://learn.sparkfun.com/tutorials/sparkfun-samd21-pro-rf-hookup-guide) Using the super blazing, nay blinding, fast SAMD21 whipping clock cycles at 48MHz and the RFM96 module to connect to the Things Network (and other Radio woodles).[Favorited Favorite](# "Add to favorites") 6[](https://learn.sparkfun.com/tutorials/qwiic-single-relay-hookup-guide) [### Qwiic 单继电器连接指南](https://learn.sparkfun.com/tutorials/qwiic-single-relay-hookup-guide) Get started switching those higher power loads around with the Qwiic Single Relay.[Favorited Favorite](# "Add to favorites") 3[](https://learn.sparkfun.com/tutorials/three-quick-tips-about-using-ufl) [### 关于使用 U.FL 的三个快速提示](https://learn.sparkfun.com/tutorials/three-quick-tips-about-using-ufl) Quick tips regarding how to connect, protect, and disconnect U.FL connectors.[Favorited Favorite](# "Add to favorites") 14[](https://learn.sparkfun.com/tutorials/cryptographic-co-processor-atecc508a-qwiic-hookup-guide) [### 加密协处理器 ATECC508A (Qwiic)连接指南](https://learn.sparkfun.com/tutorials/cryptographic-co-processor-atecc508a-qwiic-hookup-guide) Learn how to use some of the standard features of the SparkFun Cryptographic Co-processor.[Favorited Favorite](# "Add to favorites") 6

## 安全的解决方案

我们将使用数字签名来增加系统的安全性。如果你想了解更多关于如何使用密码协处理器的信息，请查看[连接指南](https://learn.sparkfun.com/tutorials/cryptographic-co-processor-atecc508a-qwiic-hookup-guide)和相关的[视频](https://youtu.be/_MjjF211BM8)。这些将向您展示数字签名背后的基本思想，带您了解如何设置每个协处理器。

[](https://learn.sparkfun.com/tutorials/cryptographic-co-processor-atecc508a-qwiic-hookup-guide) [### 加密协处理器 ATECC508A (Qwiic)连接指南

#### 2019 年 10 月 17 日](https://learn.sparkfun.com/tutorials/cryptographic-co-processor-atecc508a-qwiic-hookup-guide) Learn how to use some of the standard features of the SparkFun Cryptographic Co-processor.[Favorited Favorite](# "Add to favorites") 6

对于这里显示的安全车库门开门器的例子，我们将做一些与 Arduino 库中的[例 6](https://learn.sparkfun.com/tutorials/cryptographic-co-processor-atecc508a-qwiic-hookup-guide/example-6-challenge) 非常相似的事情。一个完整的循环将遵循以下步骤:

1.  用户按下遥控器上的按钮启动循环。
2.  远程发送“令牌请求”。
3.  Base 生成一个新的随机令牌(32 字节)。
4.  基地向远程发送令牌。
5.  远程在令牌上创建 ECC 签名(使用其唯一的私钥)。
6.  远程向基地发送 ECC 签名。
7.  Base 使用远程的公钥验证签名。
8.  如果证实，基地打开车库。

之所以如此安全，是因为世界上唯一可以创建有效签名的地方是遥控器的协处理器内部。这是因为私钥是在配置过程中随机生成的，永远不会离开 IC。如果您没有实际的硬件(远程协处理器)，您将永远无法创建签名。

此外，基地为每个周期创建一个新的随机令牌的事实，使我们能够防止[中间人](https://en.wikipedia.org/wiki/Man-in-the-middle_attack)和[滚动堵塞](https://www.wired.com/2015/08/hackers-tiny-device-unlocks-cars-opens-garages/)攻击。

哇哦！这是一个安全的无线按钮！

## 硬件概述

对于这个项目，我们需要建立两个独立的电路。一个将是遥控器(位于我的汽车或自行车中)，第二个将是位于我的车库内的基站收发器(监听 ECC 签名，然后按下车库门按钮)。

### 远程控制

*   专业射频
*   鸭触角
*   密码协处理器(用于创建 ECC 签名)
*   围场
*   纽扣
*   400 毫安时脂肪电池
*   Qwiic 电缆(数量:1)

### 基站收发器

*   专业射频
*   有线天线
*   密码协处理器(用于创建 TTL 令牌，并验证 ECC 签名)
*   SparkFun Qwiic 单继电器
*   有线天线
*   USB 壁式电源插座
*   Qwiic 电缆(数量:2)

对于简单的一键订购，这里有一个愿望清单。请务必阅读整个教程，然后根据需要进行调整。