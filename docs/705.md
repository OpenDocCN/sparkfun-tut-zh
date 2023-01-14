# 亮灯情人节卡片

> 原文：<https://learn.sparkfun.com/tutorials/light-up-valentine-cards>

## 介绍

今年情人节，用纸质电路点燃你的爱——无需焊接！本教程将指导您如何仅使用铜带、硬币电池、LilyPad 按钮板和 LED 来创建简单的纸质电路。

[![alt text](img/553a58069b4d138bb990726b3348dd03.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/Valentine-Pop-Up-Card-Tutorial-11.jpg)[![alt text](img/eac0f6ca168434f18ee1177b7f8bd188.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/Valentine-Pop-Up-Card-Tutorial-09.jpg)[![alt text](img/f27dc6a591bd191408900ad4ed056090.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/Valentine-Pop-Up-Card-Tutorial-10.jpg)

我们改编了一些免费的弹出模板用于电子产品。我们将在本教程中讨论电子构建，并链接到弹出部件的原始项目说明。

### 为什么我们不焊接？

你可能已经看过尼克精彩的[父亲节贺卡](https://learn.sparkfun.com/tutorials/light-up-fathers-day-card)教程，并想知道为什么这一张与众不同？在用品或预算有限的教室或家庭中，使用胶带和手工用品有助于降低复杂性。缺点是连接不如胶带和焊料牢固/持久。如果手头有这些材料，您可以随时使用这些模板并将元件焊接到铜带上。

另一种选择是用一小块方形的 [Z 轴导电胶带](https://www.sparkfun.com/products/12042)将元件粘在铜和元件之间，以提供比单独用胶带更牢固的连接。

### 推荐阅读

如果你刚刚接触电子产品，这里有一些有用的阅读材料供你参考:

*   [什么是电路？](https://learn.sparkfun.com/tutorials/what-is-a-circuit)
*   [发光二极管](https://learn.sparkfun.com/tutorials/light-emitting-diodes-leds)

## 材料和工具

以下是您需要遵循的所有材料和工具的列表:

*   [铜带-5 毫米宽](https://www.sparkfun.com/products/10561)(每张卡大约 18 英寸的铜带)
*   LED *请参见下面关于 LED 选择的注释
*   [纽扣电池-12 毫米(CR1225)](https://www.sparkfun.com/products/337)
*   [LilyPad 按钮板](https://www.sparkfun.com/products/8776)-或- [LilyPad 滑动开关](https://www.sparkfun.com/products/9350)
*   卡片纸(2-3 张)
*   牛皮纸或羊皮纸(可选)-在 I <3 U 设计中，为心脏中心的 led 创造一个良好的漫射效果
*   透明带
*   胶水棒/胶水
*   剪刀/业余爱好刀
*   装饰用品——贴纸、记号笔或油漆来装饰你的设计

### **关于发光二极管的说明:*

我们建议使用你能找到的最小的 LED 灯-[3 毫米](https://www.sparkfun.com/products/532)效果很好，因为它们在折叠时不会给你的卡增加太多体积。要获得额外的天赋，尝试使用自行车[RGB led](https://www.sparkfun.com/products/11448)。我们还发现，从一组 [LED 灯串](https://www.sparkfun.com/products/11752)上切下单个的 LED 灯效果很好——在使用之前，你必须用一把业余爱好刀将电线上的涂层刮掉。我们将在教程的后面讨论这个过程。请随意尝试不同的 led，找出最适合您项目的产品。

## 步骤 1:打印模板

右键单击下面的图片，然后选择“链接另存为”将模板下载到您的计算机上。每个文件都有一个回路模板页面和一个弹出模板页面。

将你的模板打印在卡片纸上。如果需要，调整打印机的页边距，或者在打印设置中选择“适合页面”。卡片模板比纸张略小，因此请确保沿着黑色边框裁剪，以获得最终的卡片尺寸。

暂时将弹出页面放在一边。我们将首先构建我们的电路，然后在电子设备安装完毕后组装弹出式菜单。

**[我< 3 U 模板](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/IHeartUPaperCircuit.pdf) - 2 页**

[![alt text](img/4e9ade75c2c92311c889dae41d46efe2.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/IHeartUPaperCircuit.pdf)

*如果你有一个剪影电子切割机，[点击这里](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/IHeartU_2.studio3)为弹出层*下载一个剪影工作室文件

**[像素心模板](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/PixelHeartPaperCircuit.pdf) - 2 页**

[![alt text](img/4ef27a72c46b7c9a54fa759eaa38d7e3.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/PixelHeartPaperCircuit.pdf)

*如果你有一个剪影电子切割机，[点击这里](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/PixelHeart_2.studio3)为弹出层*下载一个剪影工作室文件

**[框架模板](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/ValentineFramePaperCircuit_1.pdf) - 2 页**

[![alt text](img/1f2917cb816d25db09eada8048261b51.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/ValentineFramePaperCircuit_1.pdf)

*如果你有一个剪影电子切割机，[点击这里](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/FRAME.studio3)为弹出层*下载一个剪影工作室文件

## 步骤 2:创建铜迹线

是时候用铜带为我们的电开辟一条通路了。我们将用来自另一个纸电路项目的[的图片进行演示，但是这些卡片的过程是相同的。每个都有图标来帮助你构建电路。](https://learn.sparkfun.com/tutorials/let-it-glow-holiday-cards)

[![alt text](img/28f430d99ac666b33267f2fca7c5f2cd.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/Icons.png)

#### 线路 A

看一下模板，找到标有 a 的圆圈。从铜带上剥去几英寸的纸背，沿着灰线粘住。

[![alt text](img/440e10f734bdc734560794c5829515e6.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/LineA.jpg)

到达剪刀图标时剪切。

[![alt text](img/dec3aa759abb4b71e9f1652912835ed5.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/CutTape.jpg)

#### 线路 B

接下来，我们将沿线 B(包括一个角)放置胶带。为了保持拐角处铜的牢固连接，我们将使用折叠技术将胶带压制成型。

首先将铜带向下粘住，直到碰到拐角，然后将铜带向后折叠。用指甲或钢笔在边缘给它一个好的折痕。

[![alt text](img/e3a0ab56708f593de296068c428bca21.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/Corner1.jpg)

然后小心地将胶带从拐角处向下移动-你应该会看到折痕形成-并压平纸张。折叠的整洁并不重要，它最终会被你的弹出所覆盖。最后，在到达剪刀图标时剪断胶带。

[![alt text](img/593545c58e71303e660577ea1008e474.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/FoldedCorner.jpg)[![alt text](img/f95dc44334a21ef0311bf657783aef31.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/FinishedCorner.jpg)

#### C 线

最后的铜带线也将形成电池座。我们将从折叠 1/2 英寸的铜带开始，将粘合面粘在一起形成一个口盖。

[![alt text](img/d46764cc348311b12e7b547f04096762.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/FoldFlap.jpg)

这使得铜的顶部可以向下折叠到硬币电池上——电池的正极是顶部，负极是底部，这使得我们可以用铜带接触每一侧来创建一个“电池三明治”。

[![alt text](img/19adcf3649ba785d6ce2f7aa106a3e74.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/LineC.jpg)

请参见下图，了解这种方法的工作原理。我们不会安装电池，直到我们的项目结束，所以现在把它放在一边。在进入下一步之前，沿着虚线中心对折卡片。

[![alt text](img/76ae0b4b2aaa16b98dfdec7589c27bcd.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/CopperTapeBattery1.jpg)[![alt text](img/328f143cdcaaaa81b7669a076551494e.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/CopperTapeBattery2.jpg)

## 步骤 3:准备并放置 LED

*在准备 LED 之前，沿着虚线将卡片对折，这样可以省去在纸张上出现组件时试图整齐折叠的麻烦。*

现在我们的铜缆已经到位，是时候添加 LED 了。每个模板都有一个 LED 符号，它显示了一条成型的导线-我们使用这种方法来帮助我们记住 LED 的哪一面是正的，哪一面是负的。

以下是我们的[发光二极管(LED)教程](https://learn.sparkfun.com/tutorials/light-emitting-diodes-leds)中关于 LED 极性的摘录:

*“在电子学中，极性表示电路元件是否对称。发光二极管是二极管，只允许电流单向流动。当没有电流时，就没有光。幸运的是，这也意味着你不能通过反向插入来损坏 LED。相反，这是行不通的。LED 的正极称为“阳极”，以较长的“引线”或引线为标志。LED 的另一面，即负极，称为“阴极”。"*

[![alt text](img/c350d80bde66b15b00ccb803327379c6.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/LED.png)

**以下是弯曲标准 LED(如上图所示)以便为我们的电路做准备的说明。**

使用钳子(或您的手指)，将 LED 灯的较长腿弯平。然后把线做成之字形。小心不要在同一个接头上来回弯曲太多次而折断电线。

[![alt text](img/1bde680b7e269abcaf1f3e2f52aa9fb1.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/ZigZagLED.jpg)

接下来，将另一条腿弯曲成螺旋状。用钳子的末端轻轻抓住电线的末端，并将其缠绕在工具上。

[![alt text](img/6e791e02e618e7b1fd84ff0630d2a61c.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/SpiralLED.jpg)

一旦所有成型完成，将 LED 放在桌子或平面上，确保其水平直立放置。如果没有，现在就进行调整。

[![alt text](img/9306d3d7443706fef3123b03f6b4353e.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/PlaceLED.jpg)

#### 使用 LED 灯串

我们一直在尝试切割 [LED 灯串](https://www.sparkfun.com/categories/tags/fairy-light)，因为它们使用微小的 LED，非常适合像贺卡这样的平面。从灯带上切下一个 LED，确保在两边各留下约 1/2 英寸的电线。然后用业余爱好刀刮掉电线上的涂层，使其暴露出来。确保刮擦电线的四周，而不仅仅是顶部或底部，以确保您与胶带的良好连接。砂纸也可以，如果你不想用刀的话。

[![alt text](img/3151a16f9bf5ed7cbb83249d3c3b8c9e.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/ScrapingLED.jpg)

每个 LED 将有四根电线来自它——两根正极和两根负极，因为 LED 以[并联](https://learn.sparkfun.com/tutorials/series-and-parallel-circuits#parallel-circuits)的方式连接。很难立即看出哪个是哪个(它们不像普通 led 那样有方便的长/短技巧)——但我们可以根据电池快速检查它们。一旦我们知道哪一面是正面，就用记号笔在电线上做标记，以帮助识别。让电线保持笔直，而不是像另一个 LED 例子那样对它们进行整形，这是没问题的。

[![alt text](img/9ad4e789c292df3608d38da3a5bbf874.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/TestStringLight.jpg)

如果你有超强的视力，你可以检查 LED 上的绿色标记，这是消极的一面。

[![alt text](img/34279918dfdf990d4cf36262ac8d86ef.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/PreppedStringLight.jpg)

这张图片显示了一个 LED 灯串，通过识别和标记正极电线并修剪多余的电线，使它们不会意外地相互短路。

#### 胶带向下发光二极管

不管哪种类型的 LED 将被插入卡中，将正极引线与标有+的铜带对齐，负极引线与-对齐。用透明胶带将其固定在铜片上。

[![alt text](img/29a3cd50198696a315f1abcf7b94ac3f.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/TapedStringLight.jpg)

## 第四步:连接按钮

[![alt text](img/aa4018f16bafa925b83f6135d052c17f.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/ButtonDetail.png)

接下来，我们将把 LilyPad 按钮面朝上放在模板上的椭圆形图标上。哪一面接触正负并不重要。确保按钮底部的导电垫接触到铜带，然后用透明胶带封住两端。注意不要直接用胶带粘住按钮的按钮部分，否则会影响按下按钮的能力。你也可以用一个 [LilyPad 开关](https://www.sparkfun.com/products/9350)来代替按钮——安装是一样的。

[![alt text](img/fa0f0064ee6c0f037eb4ed82f7b03237.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/TapeButton.jpg)

## 第五步:插入电池

一旦所有组件安装完毕，就该通过添加电池来测试我们的电路了。小心地将电池放在我们之前制作的铜带盖下面，并将其放在圆形图标的中心。确保电池的正极(顶部，标有电池型号和+)朝上。将铜压在电池上，并用透明胶带粘住。

[![alt text](img/ef388d259f70b6ba6dbd978ec22c4774.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/BatteryFlap.jpg)

现在，按下按钮，发光二极管应该亮了！

[![alt text](img/83004f652c2aed428b3ee109e568c3a8.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/1/8/TestCard.jpg)

#### 解决纷争

*   检查胶带连接——用指甲或铅笔确保胶带将组件牢固地粘附在铜带上。
*   检查电池-确保它牢牢夹在顶部和底部铜带线之间，并且顶部铜带不会意外接触到电池底部。
*   检查 LED 灯的电线——再次检查它们是否在用钳子弯曲成各种形状时意外断裂。

完成的电路应该是这样的:

[![alt text](img/5a2f1ea1d58b9c69f98ee18c5252f9f3.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/Valentine-Pop-Up-Card-Tutorial-01.jpg)[![alt text](img/250180d75e702c5468ffa065c94a49a9.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/Valentine-Pop-Up-Card-Tutorial-02.jpg)[![alt text](img/c8b848615ce74f6e5d484e9374afb629.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/Valentine-Pop-Up-Card-Tutorial-03.jpg)

## 第六步:准备弹出

是时候剪掉我们的弹出式片段了。点击下面的链接访问弹出卡的网站，了解组装的完整说明。

### [我< 3 U 指令](http://sjrenoir.com/50033240140)

*注意:*在折叠弹出式广告之前，将一张羊皮纸或羊皮纸粘在心形图案的背面，以便于粘贴。

最初的[项目](http://sjrenoir.com/50033240140)是韩语的，所以我们包含了一个教程，我们在 youtube 上找到了一个[视频](http://youtu.be/bA6woVGmOvE?t=2m49s)向你展示了这个过程。

### [像素心指令](http://www.minieco.co.uk/valentines-day-pixely-popup-card/)

*注意:*这张[牌](http://www.minieco.co.uk/valentines-day-pixely-popup-card/)弹出来会很棘手，因为有太多的小切口。我们发现，用铅笔或薄记号笔从心脏底部到顶部一次一个地画出褶皱会更容易一些。

### [帧指令](https://learn.sparkfun.com/tutorials/let-it-glow-holiday-cards#frame)

*注意:*按照我们的圣诞弹出卡片教程中[窗口卡片](https://learn.sparkfun.com/tutorials/let-it-glow-holiday-cards#frame)的折叠说明。在相框后面用一张羊皮纸或羊皮纸做一个底座，贴上贴纸或剪纸，或者用马克笔在上面画画。我们选择了一个宠物爱好者的主题，但你可以随意创造自己独特的场景。

[![alt text](img/7ae451de1c7e139666976c8291810988.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/Valentine-Pop-Up-Card-Tutorial-04.jpg)

## 第七步:集合并欣赏

当你的弹出式广告制作完成并准备点亮时，小心地将它们放在你的铜带电路上。用胶水或胶带将边角粘到背衬上。轻轻向下折叠弹出装置，合上卡片。

最后，用记号笔或贴纸指出应该按下按钮的位置。

添加任何额外的装饰，使卡片格外特别。对于塞尔达粉丝来说，加一句“一个人去很危险！拿着这个。”pixel heart 卡外部的屏幕截图增加了一种很好的极客风格——我们从 Instructables 用户真菌 Amungus 的[版本](http://www.instructables.com/id/Zelda-Pop-Up-Valentine-Heart-Card/)的弹出卡设计中获得了一个想法。

[![alt text](img/72b25887abca832edb72b8850f8928e3.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/Valentine-Pop-Up-Card-Tutorial-05.jpg)[![alt text](img/eac0f6ca168434f18ee1177b7f8bd188.png)](https://cdn.sparkfun.com/assets/learn_tutorials/3/3/9/Valentine-Pop-Up-Card-Tutorial-09.jpg)

## 资源和更进一步

### 要尝试的事情:

*   尝试这些技术与其他弹出式设计或创建自己的-你能找出如何适应铜带路径，以适应你的卡选择？
*   在你制作好卡片后，用贴纸、颜料或记号笔使它更加个性化。

### 延伸阅读:

*   电子工艺资源 - SparkFun 的教育部门有一些关于电子工艺的可下载模板和活动。
*   [点亮父亲节卡片](https://learn.sparkfun.com/tutorials/light-up-fathers-day-card)——一张使用铜带和焊接技巧的发光卡片。
*   [让它焕发节日贺卡](https://learn.sparkfun.com/tutorials/let-it-glow-holiday-cards)——节日的纸质电路模板。