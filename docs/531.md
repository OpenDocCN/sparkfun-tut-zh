# 使用 Tessel 2 进行环境监控

> 原文：<https://learn.sparkfun.com/tutorials/environmental-monitoring-with-the-tessel-2>

## 介绍

### Phant 不再运行了

Unfortunately Phant, our data-streaming service, is no longer in service. The system has reached capacity and, like a less-adventurous Cassini, has plunged conclusively into a fiery and permanent retirement. There are several other maker-friendly, data-streaming services and/or IoT platforms available as alternatives. The three we recommend are Blynk, ThingSpeak, and Cayenne. You can read our [blog post on the topic](https://www.sparkfun.com/news/2413) for an overview and helpful links for each platform. The code in this tutorial will need to be adjusted to work with the other data streams.

在未来的世界里，我们家中的一切都将被连接起来。物联网(IoT)是这一愿景的真实体现。物联网世界包括联网设备，这些设备到目前为止还不具备如此复杂的功能。

从直观的智能恒温器开始，并扩展到其他产品的 [Nest](https://nest.com/) 产品线是不断增长的所谓“智能家居”产品市场中的一套产品。亚马逊的 [Echo](https://www.amazon.com/Amazon-Echo-Bluetooth-Speaker-with-WiFi-Alexa/dp/B00X4WHP5E) 是另一个例子，它将几个家庭集成方面整合到一个平台中。

## 我们自己的智能监控设备

智能家居系统有很多种。有些遥控家用设备，比如在特定时间自动开灯或关灯。其他人优化家庭系统的行为，也许在一天或一季的不同时间在太阳能和电网之间切换家庭的电力供应。

在本教程中，我们将专注于智能系统的*监控*方面。我们将建立一个空调监控设备来收集信息并将其存储在云中。

随着时间的推移，我们的监控设备将能够检测到以下情况:

*   不管空调是开着还是关着
*   温度
*   相对湿度
*   气压

来自设备中传感器的数据点将被上传并存储在 [Sparkfun 的虚拟 data.sparkfun.com 服务](https://learn.sparkfun.com/tutorials/pushing-data-to-datasparkfuncom/what-is-phant)中。

## 飞行前检查

如果这是你第一次试验 [Tessel 2](https://learn.sparkfun.com/tutorials/experiment-guide-for-the-johnny-five-inventors-kit/about-the-tessel-2) ，有几件事你必须先做！我们建议在开始这个项目之前通读我们的 Tessel 2 入门。我们保证，不会花那么长时间。

[](https://learn.sparkfun.com/tutorials/getting-started-with-the-tessel-2) [### 开始使用 Tessel 2

#### 2016 年 10 月 12 日](https://learn.sparkfun.com/tutorials/getting-started-with-the-tessel-2) Get your Tessel 2 up and running by blinking and LED, the Hello World of embedded electronics.[Favorited Favorite](# "Add to favorites") 1

### 深入探究 Tessel 2

如果你是从 Tessel 2 开始的话，整个 [Johnny-Five Inventor's Kit 实验指南](https://learn.sparkfun.com/tutorials/experiment-guide-for-the-johnny-five-inventors-kit)是很棒的东西。

[](https://learn.sparkfun.com/tutorials/experiment-guide-for-the-johnny-five-inventors-kit) [### Johnny-Five 发明人工具包实验指南

#### 2016 年 6 月 28 日](https://learn.sparkfun.com/tutorials/experiment-guide-for-the-johnny-five-inventors-kit) Use the Tessel 2 and the Johnny Five Inventors kit to explore the world of JavaScript enabled hardware through 14 awesome experiments![Favorited Favorite](# "Add to favorites") 8

### Phant 入门(data.sparkfun.com)

如果您以前从未使用过 data.sparkfun.com 服务，下面的指南将帮助您开始创建自己的数据采集流。

## 材料

要构建监控设备，您需要以下部件: