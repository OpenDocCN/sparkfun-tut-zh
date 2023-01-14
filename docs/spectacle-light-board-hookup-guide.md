# 眼镜灯板连接导轨

> 原文：<https://learn.sparkfun.com/tutorials/spectacle-light-board-hookup-guide>

## 眼镜灯板

眼镜灯板允许您添加一些相当复杂的照明效果到您的眼镜项目。它可以连接多达三股可寻址 led 和一个外部电源连接器。

[![Spectacle Light Board](img/5e99c37101649fb46b1a12d419443ce1.png)](https://www.sparkfun.com/products/retired/14052) 

### [眼镜灯板](https://www.sparkfun.com/products/retired/14052)

[Retired](https://learn.sparkfun.com/static/bubbles/ "Retired") DEV-14052

眼镜灯板允许您添加一些相当复杂的照明效果到您的眼镜项目中，以一种简化的…

**Retired**[Favorited Favorite](# "Add to favorites") 4[Wish List](# "Add to wish list")

### TL；灾难恢复(基本要素)

1.  如果超过大约 10 个像素将同时打开，我们建议通过板载 micro B USB 端口为灯板供电。
2.  对于数量较少的像素，可以通过眼镜控制电缆直接供电。
3.  大多数 LED 效果需要一个连续类型的信号，例如按钮板的“锁定开/锁定关”功能。
4.  只有 WS2812 (NeoPixel)型可寻址 LED 灯条可与眼镜灯板配合使用。

### 见见眼镜灯板

“眼镜灯板”旨在方便您将相对复杂的灯光效果添加到眼镜项目中，它与眼镜生态系统的其余部分相集成，让您可以相对轻松地控制灯光效果。

它有两个用于眼镜控制信号的 1/8 英寸(3.5 毫米)插孔。**注意千斤顶的方向性！**标有“In”的那一个应插入比灯板更靠近控制器板的板，或插入控制器板本身。

[![Signal jacks](img/fca4ceeb5e0bda3596d0476e10fde661.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/light_jacks.png)

灯板支持多达三股[可寻址发光二极管](https://www.sparkfun.com/products/12025)。每条线最多可以有 60 个像素。**并非所有类型的可寻址发光二极管都与眼镜灯板兼容。**如果您对特定类型的 LED 灯条是否与灯板兼容有疑问，请联系 SparkFun 技术支持。

[![LED Strand Connectors](img/8cc5fb985af6bca97d4be50ee70de3b1.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/light_connectors.png)

灯板有一个 Micro B USB 连接器，允许它直接由外部电源供电。眼镜数据传输所用的相对较细的音频电缆不足以传输超过几个像素的大量电流。

[![USB Power Jack](img/82745f21f992626f49b002431ce2685e.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/light_usb_jack.png)

### 推荐阅读

在继续之前，您应该通读[眼镜用户指南](https://learn.sparkfun.com/tutorials/spectacle-users-guide)。它会给你一些你需要了解的关于奇观如何工作的基础知识，以便你能理解本教程的其余部分。

## 配置实用程序

### 眼镜灯板

[![Action list for light board](img/7fb32688a0e009e1a5fab7b1f58b7959.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/1/light_actions_1.png)

灯光板支持 9 种不同的动作。大多数需要连续型信号输入，但也有一些可以用于瞬时输入信号。我们将在每个动作下覆盖差异。每个动作都有一个字段，表示该动作所应用到的 lightstrip 的像素数，这个字段的用法应该很明显，我们不会再提到它。

#### 彩虹效应

[![Rainbow effect settings](img/7ae77cc755ae7c2035f16f437a607972.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/1/rainbow_effect.png)

彩虹效果会在光带上显示彩虹颜色，逐个更改每个像素的颜色，使其看起来好像彩虹在光带上滚动。

*   **"而通道号...激活"** -彩虹效应仅在通道激活时持续，因此需要连续的输入信号。
*   **“彩虹卷轴光带号……”** -选择您希望彩虹效果在哪个光带上运行。要对多个 lightstrips 产生相同的效果，必须创建多个动作。
*   **滚动速度滑块** -控制图案滚动的速度。

#### 剧场追逐

[![Theater chase settings](img/c0ae3056a512269aa3fb3498a84134f4.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/1/theater_chase.png)

剧场追逐模式的行为就像一个跑马灯轻边界。灯光将向前行进，使它看起来好像光带在一步一步地移动。

*   **"而通道号...激活"** -剧院追逐效应仅在频道激活时持续，因此需要连续的输入信号。
*   **“剧场追逐光之旅号……”** -选择您希望剧院追逐效果操作的光带。要对多个 lightstrips 产生相同的效果，必须创建多个动作。
*   **追踪速度滑块** -控制图案滚动时的移动速度。
*   **颜色选择器输入** -允许你选择灯光的颜色。

#### 扫描效应

[![Scanning effect settings](img/4627216ef62940998cdf9195cf6b0bcc.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/1/scanning_effect.png)

扫描模式看到一小群光沿着光带来回跳动，让人想起《太空堡垒卡拉狄加》中的赛昂人。

*   **"而通道号...激活"** -扫描效果仅在通道激活时持续，因此需要连续的输入信号。
*   **“扫描光带号……”** -选择您希望扫描效果在哪个光带上运行。要对多个 lightstrips 产生相同的效果，必须创建多个动作。
*   **扫描速度滑块** -控制图案滚动时的移动速度。
*   **颜色选择器输入** -允许你选择灯光的颜色。

#### 闪烁效应

[![Twinkle effect settings](img/aa7bb871193593cb616557d20c7fc6d1.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/1/twinkle_effect.png)

使选定条带上的单个灯光执行闪烁动作。

*   **"而通道号...激活"** -闪烁效果仅在通道激活时持续，因此需要连续的输入信号。
*   **“一闪一闪的光带号……”** -选择您希望闪烁效果在哪个灯条上运行。要对多个 lightstrips 产生相同的效果，必须创建多个动作。
*   **颜色选择器输入** -允许你选择灯光的颜色。
*   **速度滑块** -控制闪烁发生的频率。
*   魔法滑块 -控制闪烁的魔法程度。玩吧！

#### 闪电效应

[![Lightning effect settings](img/37438395d6bef848a74bd449cfb13fc3.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/1/lightning_effect.png)

导致整个条带以看起来很像闪电的方式闪烁。

*   **"而通道号...激活"** -闪电效应仅在通道激活时持续，因此需要连续的输入信号。
*   **“light strip 号上的闪电……”** -选择您希望闪电效果在哪个光带上运行。要对多个 lightstrips 产生相同的效果，必须创建多个动作。
*   **颜色选择器输入** -允许你选择灯光的颜色。
*   **速度滑块** -控制雷击发生的频率。
*   愤怒滑块 -控制闪电有多愤怒。玩吧！

#### 火焰效果

[![Flame effect settings](img/5eed1ccba4066acc8cde31b8457ddf91.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/1/flame_effect.png)

导致整个地带像火一样噼啪作响。

*   **"而通道号...激活"** -火焰效果仅在通道激活时持续，因此需要连续的输入信号。
*   **“在光带号上生火……”** -选择你希望火焰效果在哪个光带上运行。要对多个 lightstrips 产生相同的效果，必须创建多个动作。
*   **颜色选择器输入** -允许你选择灯光的颜色。尝试不同的颜色！

#### 褪色效果

[![Fade effect settings](img/d2e7acfdfb1fb70cc37fbfe016f08428.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/1/fade_effect.png)

随着时间的推移，光带会从一种颜色变成另一种颜色，然后再变回第一种颜色。

*   **"而通道号...处于活动状态"** -只有当频道处于活动状态时，衰减效果才会持续，因此需要连续的输入信号。
*   **“淡化光带号”...back and forward "**-选择您希望淡入淡出效果在哪个灯条上操作。要对多个 lightstrips 产生相同的效果，必须创建多个动作。
*   **“从颜色”颜色选择器** -这是 lightstrip 启动时的初始颜色。
*   **"to color "拾色器** -另一种颜色，色带周期性地淡入淡出。
*   **“渐变速度”滑块** -控制渐变动作发生的速度。

#### 充满

[![Fill settings](img/cb5e9f6a3f1b3b93b98af2a5d7c90e7a.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/1/fill.png)

用单一颜色填充灯条上的一些灯光。熄灭其他灯。

*   **“收听频道号……”** -该通道上的瞬时信号是触发填充操作所需的全部，填充将持续到另一个效果开始。
*   **“等待...秒"** -这种延迟考虑到了时序效应。大多数情况下，您可能会将其设置为 0。
*   **“清除光带号……”** -选择要操作的光带。
*   **”又补...像素"** -从离灯板最近的地方向外打开的像素数。

#### 亮像素

[![Pixel settings](img/0c877049d44e68026cc8638d9d579ed9.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/1/pixel.png)

打开一盏灯，关闭其余的灯。

*   **“收听频道号……”** -该通道上的瞬时信号是触发亮像素操作所需的全部，亮像素将持续到另一个效果开始。
*   **“等待...秒"** -这种延迟考虑到了时序效应。大多数情况下，您可能会将其设置为 0。
*   **“清除光带号……”** -选择要操作的光带。
*   **"和光线像素数量... "** -像素的数量，从离灯板最近的开始，到打开。

## 示例项目

让我们用眼镜灯板拼凑一个工作项目！我们将使用“虚拟板”来闪烁连接到灯板上的灯条。

#### 连接电路板

要跟随本教程，您需要以下硬件:

[![Wall Adapter Power Supply - 5.1V DC 2.5A (USB Micro-B)](img/03a4ae2c78694f4857554e3ade8b2671.png)](https://www.sparkfun.com/products/13831) 

将**添加到您的[购物车](https://www.sparkfun.com/cart)中！**

### [壁式适配器电源- 5.1V DC 2.5A (USB Micro-B)](https://www.sparkfun.com/products/13831)

[In stock](https://learn.sparkfun.com/static/bubbles/ "in stock") TOL-13831

这是一个高品质的开关“壁式”交流到 DC 5.1V 2500ma USB 微型 B 壁式电源，专为…

$8.9521[Favorited Favorite](# "Add to favorites") 47[Wish List](# "Add to wish list")****[![Spectacle Director Board](img/d630e14f36ea53230d312085fdfe957c.png)](https://www.sparkfun.com/products/13912) 

将**添加到您的[购物车](https://www.sparkfun.com/cart)中！**

### [眼镜导演板](https://www.sparkfun.com/products/13912)

[In stock](https://learn.sparkfun.com/static/bubbles/ "in stock") DEV-13912

眼镜董事会控制着一个眼镜项目的所有行动。虽然董事会没有做太多的工作…

$24.95 $9.95[Favorited Favorite](# "Add to favorites") 4[Wish List](# "Add to wish list")****[![LED RGB Strip - Addressable, Bare (1m)](img/e2739cd253ddcba67ca46a5bfd6123ba.png)](https://www.sparkfun.com/products/retired/12025) 

### [【LED RGB 条形可寻址，裸露(1m)](https://www.sparkfun.com/products/retired/12025)

[Retired](https://learn.sparkfun.com/static/bubbles/ "Retired") COM-12025

这些是裸露的可寻址 1 米长的 5V RGB LED 灯条，每米装有 60 个 WS2812s。因为这些都是裸露的 LED

7 **Retired**[Favorited Favorite](# "Add to favorites") 13[Wish List](# "Add to wish list")[![Spectacle Light Board](img/c79a070bc46664dfcb149fbf89c19303.png)](https://www.sparkfun.com/products/retired/14052) 

### [眼镜灯板](https://www.sparkfun.com/products/retired/14052)

[Retired](https://learn.sparkfun.com/static/bubbles/ "Retired") DEV-14052

眼镜灯板允许您添加一些相当复杂的照明效果到您的眼镜项目中，以一种简化的…

**Retired**[Favorited Favorite](# "Add to favorites") 4[Wish List](# "Add to wish list")[![JST to JST-SM Wire - 1ft](img/1088191d993c587cdd53069d13d498a9.png)](https://www.sparkfun.com/products/retired/14165) 

### [JST 到 JST-SM 线-1ft](https://www.sparkfun.com/products/retired/14165)

[Retired](https://learn.sparkfun.com/static/bubbles/ "Retired") CAB-14165

这种简单的 24AWG 导线的一端与一个 JST 公接头端接，另一端与一个 JST-SM 公接头端接。每根电线…

**Retired**[Favorited Favorite](# "Add to favorites") 2[Wish List](# "Add to wish list")**** ****请注意，你将需要两根 TRRS 电缆！

首先，将 TRRS 电缆的一端插入控制器板上的“直接”插孔。

[![The direct jack](img/9ae92b5026dfe93661e222198e821fde.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/director_direct_jack.jpg)

接下来，将另一根 TRRS 电缆插入主板上的“程序”插孔。

[![The program jack](img/8c739f7de620b04fa9b4e33873570b53.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/director_program_jack.jpg)

将线缆的另一端插入手机、平板电脑或电脑的音频插孔，以便对系统进行编程。

[![Into the phone jack](img/004fa8b448e8c8ad1d9a34757cfc7f20.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/phone_audio_jack.jpg)

现在，将第一根电缆的自由端插入灯板上的“In”插孔。注意你插入的插孔，因为这两个插孔是定向的。

[![Light board input jack](img/b81d45000c2406293053b843f7d8a66d.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/Spectacle-11.jpg)

接下来，您需要 JST-SM 到 JST-PH 适配器电缆。将白色端插入灯板上的连接器位置 0。

[![Adapter into light board](img/6c6bb31d7418d4268d4180bb81364147.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/Spectacle-12.jpg)

将适配器的黑色端插入灯条上的配套连接器。

[![Adapter into light strip](img/7743e600d4a0e5ce33f008ada61698e1.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/Spectacle-13.jpg)

最后，将电源适配器的微型 B 端插入控制器板，另一端插入墙壁。您应该在灯板上看到一个稳定的灯和一个闪烁的灯。在指示板上，您会看到一个稳定的指示灯和一个闪烁一次，然后暂停，然后重复的指示灯。这表明电源已接通，板已启动并正在运行。

#### 设置板配置

[![Blank project page](img/6c65a2bce70cc035db6e44cecbf67915.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/1/bare_project_1.png)

当你第一次打开眼镜应用程序网页，这是你会看到的。你的项目名称将不同于我的，因为奇观分配一个随机的名称给每个项目。

[![add a board button](img/2c1a3f4c7a0c09deb596c39955482b9f.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/1/add_board_1.png)

要继续，我们必须告诉项目我们希望使用哪些板。首先点击页面底部的“添加电路板”按钮。

[![List of available boards](img/2bb223c10e020b359a0f6b0d033dde15.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/1/board_list_1.png)

这将显示可用电路板的列表。单击“灯”框中的任意位置，将灯板添加到系统中。

[![Light board edit button](img/f86fabc52768e08b763cc650d9e9dfc5.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/edit_button.png)

现在你已经添加了灯光板，是时候把动作添加到灯光板上了。为了获得闪烁效果，我们将在一个信号上触发两个事件，并使其中一个稍微延迟。单击上图中突出显示的隔板图标，调出分配给该板的操作列表。

[![No actions assigned](img/eab1046d9d92d6f5f2418543df45a919.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/no_actions.png)

自然，列表中没有动作，因为我们还没有添加任何动作。单击屏幕底部的“添加操作”按钮，调出可用操作列表。

[![Actions list for light board](img/9a7abc3ecec877125e587e7b9f3aea96.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/actions_list.png)

这是当你点击“添加动作”按钮时会弹出的灯板动作列表。我们想添加一个“填充颜色”类型的动作，所以单击那个条目。

[![alt text](img/63f287ee081feed6c126ebadc20b990a.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/fill_blank.png)

这是“填充颜色”动作选项列表。有关各个字段的信息，参见教程的前一页。

[![Fill with settings in place](img/42b93059b52f2bf13544e6965bb04cda.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/fill_with_options.png)

如上图所示，填写页面空白处。这将设置当事件到达通道 0 时，条带变为纯白。现在，添加另一个“填充颜色”类型的动作并向下滚动，这样它就完全可见了。

[![settings for second fill page](img/39d2802062299f0e75f5645972366050.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/second_fill_with_options.png)

一旦你添加了第二个“填充颜色”动作，如上所示设置字段。这将导致它触发与第一次填充相同的动作，但它不会在两秒钟内激活。然后，它会将长条上的所有灯设置为“黑色”(关闭)。

[![Go back button](img/b3808bd24cc9a15f4e5a320198993e05.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/go_back_button.png)

单击“返回”按钮返回主屏幕。单击此按钮也会自动保存您的工作。

现在，重复上面的步骤来添加虚拟板。单击隔板图标编辑虚拟板的操作列表。

Virtual Boards provide a number of functions outside of the normal operation of Spectacle boards. In this case, we want "Periodic Input", which generates a signal at a fixed timing rate.[![list of Virtual Board actions](img/ce730c028f760d01645520c3f5c43111.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/vb_options.png)

以下是我们可以在虚拟板上使用的操作。我们想要一个“周期性输入”，来创造我们的眨眼动作。

[![Periodic settings](img/a8f5b56c05219f38a57d21e82bb76021.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/periodic_settings.png)

您应该设置定期操作来匹配上面的设置。这将每 10 秒产生一个短脉冲。现在再次点击“返回”返回主页。

[![Finished project](img/e738830b1e04e00736350d9c976f2d2e.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/finished_project.png)

恭喜你！您已经完成了流程的配置步骤。现在是时候把这个项目放到你的董事会上了。

#### 上传

现在你已经创建了你的眼镜程序，是时候把它上传到董事会了。如果你按照上面的说明，你的上传设备已经连接到板上，可以开始了，所以你需要做的就是点击页面底部的“安装脚本”按钮。这将打开如下所示的页面。

[![Upload page](img/f195bdc5384b8dc8905d001a0e1a7d40.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/3/2/upload_page.png)

确保设备上的音量已调至最大，并且没有其他音频源(音乐、视频等)在背景中播放。然后按住控制器板上的“RST”按钮，按住“程序”按钮，然后松开“RST”按钮。

这将使主板进入程序模式。你会看到板上的灯闪烁三次，暂停，然后重复。这是电路板处于程序模式的视觉指示器。一旦您确定电路板处于编程模式，您可以通过触摸眼镜应用程序屏幕上的“安装”按钮开始编程。该按钮将在编程过程中变灰，这应该只持续几秒钟。编程完成后，您会看到指示板上的灯闪烁 10 次，暂停，然后重复。这是你的提示，程序上传成功。

再次按下“RST”按钮，重置系统并开始程序！

如果您有任何问题，请访问[故障排除页面](https://learn.sparkfun.com/tutorials/spectacle-users-guide#troubleshooting)以获得解决问题的帮助。

## 资源和更进一步

有关一般眼镜信息，请查看用户指南:

[](https://learn.sparkfun.com/tutorials/spectacle-users-guide) [### 眼镜用户指南

#### 2017 年 5 月 4 日](https://learn.sparkfun.com/tutorials/spectacle-users-guide) The Spectacle system is designed to help those without electronics or programming experience integrate electronics into projects.[Favorited Favorite](# "Add to favorites") 4

要获得更多奇观乐趣，请查看下面的附加教程:

[](https://learn.sparkfun.com/tutorials/spectacle-sound-kit-hookup-guide) [### 眼镜音响套装连接指南](https://learn.sparkfun.com/tutorials/spectacle-sound-kit-hookup-guide) All the information you need to use the Spectacle Sound Kit in one place.[Favorited Favorite](# "Add to favorites") 1[](https://learn.sparkfun.com/tutorials/spectacle-users-guide) [### 眼镜用户指南](https://learn.sparkfun.com/tutorials/spectacle-users-guide) The Spectacle system is designed to help those without electronics or programming experience integrate electronics into projects.[Favorited Favorite](# "Add to favorites") 4[](https://learn.sparkfun.com/tutorials/spectacle-audio-board-hookup-guide) [### 眼镜音频板连接指南](https://learn.sparkfun.com/tutorials/spectacle-audio-board-hookup-guide) All the information you need to use the Spectacle Audio Board in one place.[Favorited Favorite](# "Add to favorites") 2[](https://learn.sparkfun.com/tutorials/spectacle-light-kit-hookup-guide) [### 眼镜灯套件连接指南](https://learn.sparkfun.com/tutorials/spectacle-light-kit-hookup-guide) All the information you need to use the Spectacle Light Kit in one place.[Favorited Favorite](# "Add to favorites") 2[](https://learn.sparkfun.com/tutorials/spectacle-button-board-hookup-guide) [### 眼镜按钮板连接导轨](https://learn.sparkfun.com/tutorials/spectacle-button-board-hookup-guide) All the information you need to use the Spectacle Button Board in one place.[Favorited Favorite](# "Add to favorites") 2[](https://learn.sparkfun.com/tutorials/spectacle-motion-board-hookup-guide) [### 眼镜运动板连接指南](https://learn.sparkfun.com/tutorials/spectacle-motion-board-hookup-guide) All the information you need to use the Spectacle Motion Kit in one place.[Favorited Favorite](# "Add to favorites") 2[](https://learn.sparkfun.com/tutorials/spectacle-inertia-board-hookup-guide) [### 眼镜惯性板连接导轨](https://learn.sparkfun.com/tutorials/spectacle-inertia-board-hookup-guide) Everything you need to know about using the Spectacle Inertia Board in one place.[Favorited Favorite](# "Add to favorites") 2[](https://learn.sparkfun.com/tutorials/spectacle-example-super-mario-bros-diorama) [### 奇观例子:超级马里奥兄弟西洋镜](https://learn.sparkfun.com/tutorials/spectacle-example-super-mario-bros-diorama) A study in building an animated diorama (with sound!) using Spectacle electronics.[Favorited Favorite](# "Add to favorites") 1

或者查看使用眼镜灯板的博客项目帖子:

[](https://www.sparkfun.com/news/2380 "May 10, 2017: Stand out at graduation using the Spectacle ecosystem to decorate your cap!") [### 硬件驼峰日:成为毕业典礼上的奇观！

May 10, 2017](https://www.sparkfun.com/news/2380 "May 10, 2017: Stand out at graduation using the Spectacle ecosystem to decorate your cap!")[Favorited Favorite](# "Add to favorites") 0[](https://www.sparkfun.com/news/2386 "May 16, 2017: The good, the bad and the $700 IoT cold-press juice machine.") [### 周日:从 Juicero 到 Juicezero

May 16, 2017](https://www.sparkfun.com/news/2386 "May 16, 2017: The good, the bad and the $700 IoT cold-press juice machine.")[Favorited Favorite](# "Add to favorites") 1[](https://www.sparkfun.com/news/2401 "October 4, 2017: Adding some cyberpunk dystopia style to a costume shop parasol") [### 硬件驼峰日:银翼杀手阳伞

October 4, 2017](https://www.sparkfun.com/news/2401 "October 4, 2017: Adding some cyberpunk dystopia style to a costume shop parasol")[Favorited Favorite](# "Add to favorites") 1****