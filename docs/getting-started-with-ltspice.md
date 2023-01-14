# LTspice 入门

> 原文：<https://learn.sparkfun.com/tutorials/getting-started-with-ltspice>

## LTspice 简介

[线性技术](http://www.linear.com/)提供有用且*免费的* [设计模拟工具](http://www.linear.com/designtools/software/)以及器件模型。本教程将涵盖使用 LTspice IV(一个免费的集成电路模拟器)的基础知识。

## 入门指南

要下载 Windows 版 LTspice IV，请点击[此处](http://ltspice.linear-tech.com/software/LTspiceIV.exe)，要下载 Mac OS X 10.7+版，请点击[此处](http://ltspice.linear-tech.com/LTspiceIV.dmg)。线性技术更新这些包，所以检查[网站](http://www.linear.com/designtools/software/#LTspice)的更新。我链接了可执行文件，因为这是我将在教程中使用的版本。

**Note:** For Ubuntu Linux users, you can look into using a Wine derivative called PlayOnLinux. One of our customers tested it out with Ubuntu. You can check out their [forum post](https://electronics.stackexchange.com/questions/18760/comparison-between-spice-simulators/43329#43329) for more information.

Here are some installation guides for PlayOnLinux:

*   [PlayOnLinux Ubuntu 文档](https://help.ubuntu.com/community/PlayOnLinux)
*   如何安装 PlayOnLinux？

打开 LTspice IV 实例后，查看下面的视频，了解如何开始浏览菜单、设置原理图和波形首选项、添加新原理图、放置器件和组织原理图，以及最后在分压器上运行简单的 DC 工作点。

[https://www.youtube.com/embed/FWGC9SqA3J0/?autohide=1&border=0&wmode=opaque&enablejsapi=1](https://www.youtube.com/embed/FWGC9SqA3J0/?autohide=1&border=0&wmode=opaque&enablejsapi=1)

### 有用的提示

[热键和模拟器指令](http://cds.linear.com/docs/en/software-and-simulation/LTspiceIV_flyer.pdf) -快捷方式让您的生活更轻松。模拟器指令是您的点命令。我建议您在 LTspice 的帮助菜单中仔细查看这些内容。“帮助”菜单将向您显示语法并给出每个语法的描述。具体命令将在以后的视频中逐一介绍。如果你有一个或多个问题，请访问论坛。

[标签](http://cds.linear.com/docs/en/software-and-simulation/LTspiceGettingStartedGuide.pdf) -翻到第 23 页，看看如何标记数值，例如用 8k 代替 8000。

## 模拟:瞬态分析

时域瞬态分析是指绘制电压或电流等参数相对于时间的曲线。如果您正在查看输出，您可以看到特定时间长度内的行为。在这个例子中，我们将模拟一个半波整流器的输出。对于这种类型的分析，我们将介绍如何在原理图中添加交流信号源并选择特定的二极管。

[https://www.youtube.com/embed/X8xdeQfKhx4/?autohide=1&border=0&wmode=opaque&enablejsapi=1](https://www.youtube.com/embed/X8xdeQfKhx4/?autohide=1&border=0&wmode=opaque&enablejsapi=1)

## 模拟:交流分析

交流分析提供电路的频率响应。输出波形将是一个[波特图](http://lpsa.swarthmore.edu/Bode/Bode.html)，显示指定频率范围内的幅度和相位。交流分析有几个选项。在笛卡尔坐标平面上，频率响应可以用实轴和虚轴表示，也可以用奈奎斯特图表示。

我们将构建一个无源、一阶、[低通滤波器](http://www.electronics-tutorials.ws/filter/filter_2.html)，看看从图中可以获得什么样的电路信息。

[https://www.youtube.com/embed/FR29PyRc_Tg/?autohide=1&border=0&wmode=opaque&enablejsapi=1](https://www.youtube.com/embed/FR29PyRc_Tg/?autohide=1&border=0&wmode=opaque&enablejsapi=1)

## 模拟:DC 扫描

DC 扫描是一种模拟，允许您改变特定设备的电压或电流。在 SparkFun 零件的所有原理图上，我们给你一个产品可以安全运行的电压范围。我认为这将是一个好主意，检查 Sparkfun 产品，看看这些电压范围有多准确。在本例中，我们将看看[驻极体话筒转接板](https://www.sparkfun.com/products/12758)。

[https://www.youtube.com/embed/Iq4N4UaJ4v4/?autohide=1&border=0&wmode=opaque&enablejsapi=1](https://www.youtube.com/embed/Iq4N4UaJ4v4/?autohide=1&border=0&wmode=opaque&enablejsapi=1)

## 模拟:噪音

[噪声分析](http://www.ni.com/tutorial/14516/en/)可让您查看系统固有的噪声，以及正确建模时外部源注入的噪声。在精度至上的运算放大器电路中，噪声是最常见的问题。例如，电池管理系统使用运算放大器来检测电流。可充电电池的充电周期以及负载电流是监控电池整体健康和用户安全的非常重要的参数。高噪声运算放大器电路可能会扭曲电流读数，并导致不必要的影响，例如微控制器上的不正确电流读数，从而防止电池过流或欠流。我相信在这里使用音频示例会更好。但是你应该知道，当不需要的时候，噪音是有害的。

我们将继续使用驻极体麦克风分线板的前置放大器电路，并进行噪声分析。LTspice 可以对电路的[拍摄、闪烁和热](https://en . Wikipedia . org/wiki/Noise _(电子)噪声)进行建模。

[https://www.youtube.com/embed/IUxua3jeZQo/?autohide=1&border=0&wmode=opaque&enablejsapi=1](https://www.youtube.com/embed/IUxua3jeZQo/?autohide=1&border=0&wmode=opaque&enablejsapi=1)

## 模拟:DC 转移

DC 传递函数计算电路的低频增益以及输入和输出电阻。继续以驻极体话筒分线板产品为例，我们可以先计算传递函数。我们知道，输出电压偏置为输入电压的 1/2。因为传递函数将输出的行为描述为输入的函数，我们可以说传递函数应该等于 1/2。如果我们选择 VCC 为 5V，则 Vout 为 2.5V。该电路应具有低输出阻抗，因为我们希望运算放大器像理想电压源一样工作。这可确保输出端提供最大功率，从而为 ADC 提供最佳值。输出阻抗越接近零越好。同样，我们希望输入阻抗较高，以免从源中汲取电流。让我们模拟传递函数，并验证它是否经过相应的设计。

[https://www.youtube.com/embed/Citk1YVUsHA/?autohide=1&border=0&wmode=opaque&enablejsapi=1](https://www.youtube.com/embed/Citk1YVUsHA/?autohide=1&border=0&wmode=opaque&enablejsapi=1)

## 创建新模型

在 LTspice 中创建自己的模型有几个步骤。一个模型由一个子电路和一个符号组成。例如，我们将为电位计建立一个模型。它将基于 SparkFun 10k trimpot。几个月前，我基于 555 定时器设计了一个个人使用的焊接套件。LTspice 没有标准电位计，因此我们将制作一个。大多数情况下，将调整电位计模拟为电阻是没问题的。但我计划将这个套件给电子专业的新生，希望他们理解电阻符号及其用途与电位计符号之间的区别，以及如何在本电路中使用。

参见下面的视频，在 LTspice 中创建您自己的电位计模型。

[https://www.youtube.com/embed/LUTON6WkwCg/?autohide=1&border=0&wmode=opaque&enablejsapi=1](https://www.youtube.com/embed/LUTON6WkwCg/?autohide=1&border=0&wmode=opaque&enablejsapi=1)

## 添加第三方模型

有许多方法可以将第三方模型导入 LTspice。我发现了一种导入模型和子电路最快最简单的方法。最后，我会在论坛上添加另一个视频，告诉大家如何用其他方法做到这一点。如果你有适合你的方法，请在论坛上分享。如果你在使用特定的方法上有困难，请在论坛上提问，我会用一段视频来回应。

[https://www.youtube.com/embed/OcnZnHd6Zdk/?autohide=1&border=0&wmode=opaque&enablejsapi=1](https://www.youtube.com/embed/OcnZnHd6Zdk/?autohide=1&border=0&wmode=opaque&enablejsapi=1)

## 资源和更进一步

*   查看 LTspice 的新[论坛](https://forum.sparkfun.com/viewforum.php?f=53)！在这里，您可以提出问题、发布解决方案、从教程中获取示例电路、每周观看新视频以及寻找 LTspice 社区。我知道有很多关于 LTspice 的论坛，但是一个新鲜的论坛是很棒的。

*   [这里](https://www.youtube.com/playlist?list=PL4vooS_8RnzE4EoE27QssuxsccFmspbRP)是线性科技放的一些视频教程。

*   来自 Linear Technology 的 LTspice [入门指南](http://cds.linear.com/docs/en/software-and-simulation/LTspiceGettingStartedGuide.pdf)。

*   该列表将定期更新。