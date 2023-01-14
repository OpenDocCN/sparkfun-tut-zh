# 在爱迪生上使用液晶显示器

> 原文：<https://learn.sparkfun.com/tutorials/using-an-lcd-on-the-edison>

## 介绍

我们经常听到的对英特尔爱迪生的要求之一是能够使用液晶显示器。虽然 Edison 没有显示驱动器，但我们可以使用板载 SPI 端口来控制简单的 LCD。

替换打开

[https://www.youtube.com/embed/zSXiwJJw4KE](https://www.youtube.com/embed/zSXiwJJw4KE)

替换关闭

对于这个特别的教程，我们将依赖于英特尔的 [UPM 库](https://github.com/intel-iot-devkit/upm)的最新版本。它是一个模块，能够调用必要的函数来控制 ILI9341 驱动芯片，这是一个流行的 320x240，2”-3”液晶显示器的控制器。

**NOTE:** The UPM driver used in this tutorial is a library that works in *user space*. That means we can make function calls to draw simple shapes and text on the LCD. Because it is not in *kernel space* we cannot do things like run [X](https://en.wikipedia.org/wiki/X_Window_System) on it.**ALSO NOTE:** The SPI driver on the Edison is currently quite slow. A full-screen refresh takes around 20 seconds, so don't expect any video or fast cycling images. If the SPI driver is updated in a future Edison image, you can ignore this message.

### 所需材料

你需要一个带 ILI9341 控制器的液晶显示器。这些可以从各种来源找到，比如 PJRC 的[和 T2 的](https://www.pjrc.com/store/display_ili9341.html)。此外，您还需要以下物品: