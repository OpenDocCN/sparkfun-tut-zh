# 眼镜音频板连接指南

> 原文：<https://learn.sparkfun.com/tutorials/spectacle-audio-board-hookup-guide>

## 眼镜音频板

眼镜音频板允许您添加声音到您的眼镜项目。它接受带有声音的 microSD 卡。ogg 格式(稍后将详细介绍)，并有一个 1/8 英寸(3.5 毫米)音频插孔来连接外部放大器。

[![Spectacle Audio Board](img/b36e75ebbd77f930374eafd7148c72ee.png)](https://www.sparkfun.com/products/retired/14034) 

### [眼镜音频板](https://www.sparkfun.com/products/retired/14034)

[Retired](https://learn.sparkfun.com/static/bubbles/ "Retired") DEV-14034

眼镜音频板允许您将 microSD 卡中的声音添加到您的眼镜项目中。每个板接受一个微型…

**Retired**[Favorited Favorite](# "Add to favorites") 5[Wish List](# "Add to wish list")

### TL；灾难恢复(基本要素)

1.  眼镜的音频文件应格式化为。奥格文件。
2.  音频文件应该有名称 00.ogg、01.ogg、02.ogg 等。
3.  音频板上的音频插孔产生仅适用于放大的输出。它不适合耳机或无电源扬声器。

### 认识一下眼镜音频板

眼镜音频板旨在成为一种低成本且易于使用的向项目添加声音的方法，它与眼镜生态系统的其余部分相集成，以按需提供声音效果。

它有三个 1/8 英寸(3.5 毫米)插孔:两个用于眼镜控制信号，一个用于音频输出。确保将电缆插入正确的插孔！将音频设备插入其中一个眼镜插孔可能会损坏音频设备。请注意，眼镜数据插孔是定向的:标有“In”的插孔应插入“上游”板(即比这个更靠近控制器板)，标有“Out”的插孔连接到下一个下游板。**“输出”插孔不用于音频信号。**

[![Spectacle IO jacks](img/9614ba71f6bd48a8e38b2e2f2da20a7d.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/audio_io_jacks.png)

音频输出仅为放大设备设计。这意味着任何使用带耳机或未放大扬声器的眼镜音频板的尝试都将无法产生声音输出。SparkFun 出售一款[小型、放大、可充电扬声器](https://www.sparkfun.com/products/14023)，专门用于眼镜音频板。

[![Audio jack](img/49c3e2513872241cbca37cfb29b7812b.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/audio_audio_jack.png)

眼镜音频板使用微型 SD 卡存储要播放的音频文件。这些文件应该存储为。ogg Vorbis 编码文件。这种免费的音频文件格式可以在任何类型的计算机上播放和创建。在教程的后面，我们将向您展示如何从 MP3、WAV 或其他文件格式转换为。ogg 格式。

[![SD Card Slot](img/7aa1f46ff8a936eaec429bea199d13f2.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/audio_sd.png)

这些文件必须用数字命名，这是在配置应用程序中引用它们的方式。文件名示例有 00.ogg、01.ogg、02.ogg 等等。

### 推荐阅读

在继续之前，您应该通读[眼镜用户指南](https://learn.sparkfun.com/tutorials/spectacle-users-guide)。它会给你一些你需要了解的关于奇观如何工作的基础知识，以便你能理解本教程的其余部分。

## 配置实用程序

### 眼镜音频板

[![Sound interface](img/beeaf5304cbaa32bf9bc8248b2339563.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/spectacle_app_audio_play_1.png)

眼镜音频板只支持一个动作:播放声音。正如您在上面看到的，有许多设置与这个动作相关联。

*   **“收听频道号……”** -这是触发音频开始播放的频道号。只要该频道的值高于阈值水平(见下文)，声音将以由下面指定的两个时间间隔确定的速率重复播放。
*   **“等等...秒和播放……”** -这是系统中的第一次延迟。通过延迟声音播放时间，您可以按照自己认为合适的方式对事件进行排序。
*   **...还有播放文件号……”** -这是你告诉棋盘玩哪个文件的地方。记住，将音频文件复制到 Micro SD 卡时，要命名为 00.ogg、01.ogg、02.ogg 等。此栏中的数字对应于音频文件名称中的数字。如果没有相应编号的音频文件，将不会播放任何声音。
*   **“不要让另一个声音打断，直到...秒"** -该字段中的数字应与音频文件的长度相对应。如果这个值小于声音文件的长度，发送到音频板的另一个触发器将在声音结束前中断声音。如果比声音长，播放后会有一段时间的静默，然后才能开始另一次播放。
*   **“激活阈值”**——就像 app 里说的，大部分时候你不需要调整这个。通过调整这个，你可以设置眼镜加速板触发声音的角度，或者随机触发虚拟板引起声音播放的频率。

## 将声音转换为 OGG Vorbis 格式

眼镜音频板使用的文件必须是 OGG Vorbis 格式。这种免费的有损编解码器具有比 MP3 更高的压缩比，更重要的是，可以在无需向任何第三方组织支付许可费的情况下使用。

#### 下载并安装 Audacity

我们将使用[免费开源程序“Audacity”](http://www.audacityteam.org/)将你的文件从当前格式转换成 OGG Vorbis 格式。

[![Audacity website](img/175bd8b41282f0655b5e0634e07ef9f9.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/audacity_website.png)

Audacity 可以在所有三个主要的操作系统上使用，所以安装它不会有任何问题。

当您启动 Audacity 时，您会看到这个屏幕，或者一个非常类似的屏幕。乍一看，这似乎非常复杂，**这些废话对我们来说都不重要，**所以不要惊慌。

[![Audacity main screen](img/2c42da842b8e18b9f4ab77ad74c6f81e.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/audacity_5.png)

#### 载入文件

像大多数程序一样，“加载文件”只是意味着从“文件”菜单中选择“打开”并选择你想要转换的文件。Audacity 能够编辑大多数类型的音频文件:WAV、AIFF、FLAC、MP3 等。

[![Audacity file menu](img/d78dd50a3303e4cd9847fb302e490a20.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/audacity_open.png)

默认情况下，当您打开打开对话框时，Audacity 会显示所有文件，而不仅仅是兼容的音频文件。有一个下拉菜单允许你改变它，所以它只显示兼容的音频文件沿着窗口的底部边缘。

[![Audacity open file dialog](img/a41718be862d88c629c22252ceeb7e7e.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/audacity_open_window.png)

一旦你选择了你想要编辑的文件，一个相当危言耸听的消息可能会弹出，警告你不要在没有拷贝的情况下编辑文件。点击“确定”即可。

[![Audacity edit file warning](img/e33e203f3f78b72102e250bda07bd5a2.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/audacity_warning.png)

你会看到，这样的东西出现了。这是你的音频文件在电脑上的样子。**还是那句话，不要慌！**除非你想以某种方式编辑声音(我们不这样做)，否则这里弹出的所有设置或信息对我们来说都不重要。

[![Audacity with open file](img/d8220d68d44437d4cc3be0bf0f596d17.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/audacity_file_open.png)

#### 皈依 OGG 教

现在您已经加载了文件，您需要将其转换为 OGG Vorbis 格式。为此，请打开“文件”菜单并选择“导出音频...”菜单项大约在中间。应该会弹出一个熟悉的保存窗口。

[![Export command in file menu](img/1011ff0c6124afa8f3e0c25e87c1c188.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/audacity_export_audio_1.png)

在“文件名:”字段的正下方，您会看到一个标有“保存类型:”的下拉菜单。在下拉列表中选择“Ogg Vorbis 文件”。

窗口底部会出现一个滑块。默认值“5”对于大多数目的来说可能已经足够了。点击“保存”,会弹出另一个窗口。

[![Export audio frame](img/936635ab07c45bb12ef1b3cb98c5a503.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/audacity_export_audio_frame.png)

这个允许你设置文件的元数据。你可以忽略一切，只需点击“确定”跳过这一步。

恭喜你！您已成功将文件转换为 OGG Vorbis 格式。您现在可以将该文件复制到 Micro SD 卡(不要忘记将其重命名为一个数字！)与眼镜音频板一起使用。

[![Set metadata window](img/e7a2874971a434962645fc919018322a.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/metadata.png)

#### 额外加分——减少脂肪，让声音更大

正如你在我上面的文件中看到的，声音的范围和窗户的范围之间有很大的空间。在时间轴(水平轴)上，这表现为声音文件内容前后的平线。在“响度”(垂直)轴中，这表现为波形文件顶部和底部以及回放位置窗口顶部和底部之间的空间。

[![File open in Audacity](img/d8220d68d44437d4cc3be0bf0f596d17.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/audacity_file_open.png)

让我们消除声音播放前后的一些停滞时间。为此，只需在回放位置窗口内单击并拖动，就像您试图选择一段文本一样。如上所述，您选择的部分将被突出显示。现在，只需按下键盘上的“删除”键，该部分就会被删除。在声音的另一端重复这个过程。

[![Extra dead time highlighted](img/d2d40f72fb638924d972a06c9700e1fa.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/audacity_highlighted_extra.png)

现在，让我们看看我们能做些什么。在“编辑”菜单下，找到“选择”子菜单，选择“全部”来选择整个声音。你也可以使用上面的拖拽高亮方法。

[![Finding the "Select All" menu option](img/083b82d40c41b3720ea9d3c9c3f1ec87.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/select_all.png)

现在你已经选择了整个声音，点击“效果”菜单并选择“放大…”选项。

[![Effects menu](img/3d6c82fbcdae71dd5da95bc671dc47fb.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/effects_menu.png)

将弹出一个新窗口，带有一个滑块、几个文本框和一个复选框。滑块将被预先定位，以在不“削波”声音的情况下尽可能放大声音。当您试图将声音放大到播放系统无法承受的程度时，就会发生“削波”,这会导致播放过程中出现一种刺耳的嗡嗡声。

[![Amplify dialog box](img/113ced14066478386d78298e4d2a3910.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/amplify_dialog.png)

现在你有一个选择:你可以接受系统建议的级别，或者你可以点击“允许剪辑”复选框，用滑块增加放大倍数。我已经选择接受上图的剪裁限制；将它与更高的文件图像进行比较，您可以看到我是如何修剪末端的停滞时间并垂直增加振幅的。

为什么你想让你的声音剪辑？嗯，首先，预设的放大倍数只考虑了你声音的峰值，所以如果允许剪辑一小部分音频，可能会让绝大多数声音大很多。第二，如果你的播放设备质量相对较差，或者声音文件本身质量较差，允许剪辑可能会显著增加音量，而不会使声音质量比原来差太多。第三，音量强度可能比音质更重要，允许削波可以让你尽可能地提高音量。

[![Edited sound](img/4fee1fbb68168bce4daa1b378a95a6be.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/1/8/edited_sound.png)

现在你已经成功地编辑了声音，按照我们上面提到的，把它导出到 OGG Vorbis。

## 示例项目

让我们使用眼镜音频板随机播放单个声音。

#### 连接电路板

本教程需要以下硬件:

[![microSD USB Reader](img/37e2c25218d6b05b9956f85a76c5cee6.png)](https://www.sparkfun.com/products/13004) 

将**添加到您的[购物车](https://www.sparkfun.com/cart)中！**

### [microSD USB 读卡器](https://www.sparkfun.com/products/13004)

[In stock](https://learn.sparkfun.com/static/bubbles/ "in stock") COM-13004

这是一个很棒的微型 USB 读卡器。只需将您的 microSD 卡滑入 USB 连接器内部，然后将它插入 USB 连接器

$5.5011[Favorited Favorite](# "Add to favorites") 11[Wish List](# "Add to wish list")****[![Wall Adapter Power Supply - 5.1V DC 2.5A (USB Micro-B)](img/03a4ae2c78694f4857554e3ade8b2671.png)](https://www.sparkfun.com/products/13831) 

将**添加到您的[购物车](https://www.sparkfun.com/cart)中！**

### [壁式适配器电源- 5.1V DC 2.5A (USB Micro-B)](https://www.sparkfun.com/products/13831)

[In stock](https://learn.sparkfun.com/static/bubbles/ "in stock") TOL-13831

这是一个高品质的开关“壁式”交流到 DC 5.1V 2500ma USB 微型 B 壁式电源，专为…

$8.9521[Favorited Favorite](# "Add to favorites") 47[Wish List](# "Add to wish list")****[![Hamburger Mini Speaker](img/f740a9a9bf0089b02ff8b3e1641c5d72.png)](https://www.sparkfun.com/products/14023) 

将**添加到您的[购物车](https://www.sparkfun.com/cart)中！**

### [汉堡迷你音箱](https://www.sparkfun.com/products/14023)

[In stock](https://learn.sparkfun.com/static/bubbles/ "in stock") COM-14023

这对你的耳朵将是一种享受！汉堡包迷你扬声器是一个 3W 的经济扬声器选项，适用于任何需要标准扬声器的项目

$5.502[Favorited Favorite](# "Add to favorites") 20[Wish List](# "Add to wish list")****[![Spectacle Director Board](img/d630e14f36ea53230d312085fdfe957c.png)](https://www.sparkfun.com/products/13912) 

将**添加到您的[购物车](https://www.sparkfun.com/cart)中！**

### [眼镜导演板](https://www.sparkfun.com/products/13912)

[In stock](https://learn.sparkfun.com/static/bubbles/ "in stock") DEV-13912

眼镜董事会控制着一个眼镜项目的所有行动。虽然董事会没有做太多的工作…

$24.95 $9.95[Favorited Favorite](# "Add to favorites") 4[Wish List](# "Add to wish list")****[![microSD Card with Adapter - 16GB (Class 10)](img/6f7aff013a358c1d4fb60a8f997c9c9d.png)](https://www.sparkfun.com/products/retired/13833) 

### [带适配器的 microSD 卡——16GB(10 类)](https://www.sparkfun.com/products/retired/13833)

[Retired](https://learn.sparkfun.com/static/bubbles/ "Retired") COM-13833

这是一个 10 级 16GB microSD 存储卡，非常适合容纳单板计算机和多种…

6 **Retired**[Favorited Favorite](# "Add to favorites") 8[Wish List](# "Add to wish list")[![Spectacle Audio Board](img/24d415da9b7673df09358eae37805619.png)](https://www.sparkfun.com/products/retired/14034) 

### [眼镜音频板](https://www.sparkfun.com/products/retired/14034)

[Retired](https://learn.sparkfun.com/static/bubbles/ "Retired") DEV-14034

眼镜音频板允许您将 microSD 卡中的声音添加到您的眼镜项目中。每个板接受一个微型…

**Retired**[Favorited Favorite](# "Add to favorites") 5[Wish List](# "Add to wish list")[![Audio Cable TRRS - 3ft](img/42d4d559a54ced635d43584680ec16b1.png)](https://www.sparkfun.com/products/retired/14164) 

### [音频线 TRRS - 3ft](https://www.sparkfun.com/products/retired/14164)

[Retired](https://learn.sparkfun.com/static/bubbles/ "Retired") CAB-14164

这是一条 3 英尺长的白色音频电缆，两端各有两个 TRRS 连接器。TRRS 连接器是…

**Retired**[Favorited Favorite](# "Add to favorites") 5[Wish List](# "Add to wish list")******** ********你需要两根 TRRS 电缆。在您第一次尝试使用扬声器之前，请确保它已充电！

首先，将 TRRS 电缆的一端插入控制器板上的“直接”插孔。

[![The direct jack](img/9ae92b5026dfe93661e222198e821fde.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/director_direct_jack.jpg)

接下来，将另一根 TRRS 电缆插入主板上的“程序”插孔。

[![The program jack](img/8c739f7de620b04fa9b4e33873570b53.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/director_program_jack.jpg)

将线缆的另一端插入手机、平板电脑或电脑的音频插孔，以便对系统进行编程。

[![Into the phone jack](img/004fa8b448e8c8ad1d9a34757cfc7f20.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/9/phone_audio_jack.jpg)

现在，您需要将第一根 TRRS 电缆的另一端(连接到“直接”插孔的一端)连接到音频板上的“输入”插孔。

[![In jack on Audio Board](img/ad9d179b4645bb6bdc07a6d0cc8dbb7b.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/Spectacle-14.jpg)

将扬声器连接到音频板上的“音频输出”端口。

[![Audio jack to speaker connection](img/fd407ae9c2228e26a3ce5cd4a1eacac7.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/Spectacle-15.jpg)

最后，将准备好文件的 microSD 卡插入声卡背面的插槽中。

[![MicroSD card insertion](img/4c2877b710582a4900ac0834f4875716.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/Spectacle-16.jpg)

最后，将电源适配器的微型 B 端插入控制器板，另一端插入墙壁。您应该在音频板上看到一个稳定的灯和一个闪烁的灯，在指示板上，您将看到一个稳定的灯和一个闪烁一次，然后暂停，然后重复的灯。这表明电源已接通，板已启动并正在运行。

#### 设置板配置

我们将假设您遵循了[上一页](https://learn.sparkfun.com/tutorials/spectacle-audio-board-hookup-guide#converting-sounds-to-ogg-vorbis-format)中关于将声音转换为 OGG Vorbis 格式的说明，并且在插入声卡的 Micro SD 卡上有一个名为“00.ogg”的声音。如果是*而不是*这种情况，花几分钟时间回到那一页，准备一段录音。

当你第一次打开眼镜应用程序网页，这是你会看到的。你的项目名称将不同于我的，因为奇观分配一个随机的名称给每个项目。

[![Blank project page](img/89dd847b145e98da99a53e100d51cb4a.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/bare_project.png)

你要做的第一件事就是给项目添加一个音频板。为此，请单击下图中突出显示的“添加电路板”按钮。

[![Add a board button](img/5b1fe5bdd06d4ccb5fd950ef535542a0.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/add_new_board_button.png)

点击该按钮将显示可用电路板的列表。单击“音频”框中的任意位置，为您的系统添加音频板。

[![Board list](img/5eceeda78b19ddddbabe298617142638.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/board_list.png)

我们现在需要告诉系统我们想要这个板做什么。

在你点击“音频”框后弹出的屏幕中，你会发现这个小隔板图标。单击该图标将动作添加到音频板。

[![Edit button](img/5e10633b0c34d647078411dce0bb66fa.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/sound_board_edit_button.png)

这将打开该板的“操作”列表，该列表目前为空。要添加操作，请单击下面突出显示的“添加操作”按钮。

[![Add action button](img/705b8f65499f76fc5d109524a2a4eef5.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/add_action_button.png)

点击“添加操作”按钮将下拉这个短菜单，上面只有两个选项。单击“播放声音”,向白板添加声音播放动作。

[![Actions list for the audio board](img/1e7608bd4a652a3652e886852421c1c5.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/actions_list.png)

这是“播放声音”动作设置页面。我们已经在本教程的其他地方讨论了这些字段[的含义，所以我将告诉你在这些字段中输入什么。](https://learn.sparkfun.com/tutorials/spectacle-audio-board-hookup-guide#the-configuration-utility)

[![Play sound action options](img/ab69a46d885ef4e9654365a24ea8cb5b.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/play_sound_action.png)

将下图中的设置复制到字段中。

[![Settings for the play sound action](img/a893f160df5b01b48ebfb93d2cc95966.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/play_sound_action_filled.png)

现在点击页面底部的“返回”按钮。您刚才输入的设置将被自动保存，您将返回到项目的主页。

[![Go Back Button highlighted](img/7f0539115e313eb8ddf07b69e1aea6d8.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/go_back_button.png)

现在，您返回到主页，您可以看到我们刚刚在音频板配置中设置的操作也显示在板列表中，以提醒您该板的配置用途。

[![Main page with new actions](img/f24f804c476637bf0f7f4f3ffd76a8d7.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/main_page_with_board.png)

现在，单击“添加电路板”再次调出电路板列表，然后单击“虚拟”向系统添加虚拟电路板。这个“板”将产生随机触发音频播放的信号。

Virtual Boards provide a number of functions outside of the normal operation of Spectacle boards. In this case, we want "Random Input", which generates a signal at a fixed timing rate.

再次单击虚拟板列表项上的隔板图标，以显示操作添加和编辑页面。

以下是虚拟董事会可能采取的行动列表。点击“随机输入”获得我们想要的随机函数。

[![Virtual board actions list](img/fd8ab545bd529b32d56315b77a4a7b13.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/virtual_board_actions.png)

如下图所示配置随机输入设置，然后单击“返回”按钮返回主页。

[![Random function settings](img/f1c24dc476ef85f3ad249ab477d55e57.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/random_input.png)

恭喜你！您已经完成了系统配置。现在是时候将设置安装到控制器板上了。

[![Final project screen](img/d4c3f7241fa88223322143b69d124616.png)](https://cdn.sparkfun.com/assets/learn_tutorials/6/2/3/all_board_all_actions.png)

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

[](https://learn.sparkfun.com/tutorials/spectacle-users-guide) [### 眼镜用户指南](https://learn.sparkfun.com/tutorials/spectacle-users-guide) The Spectacle system is designed to help those without electronics or programming experience integrate electronics into projects.[Favorited Favorite](# "Add to favorites") 4[](https://learn.sparkfun.com/tutorials/spectacle-light-and-sound-kit-hookup-guide) [### 眼镜灯光和声音套件连接指南](https://learn.sparkfun.com/tutorials/spectacle-light-and-sound-kit-hookup-guide) All the information you need to use the Spectacle Light and Sound Kit in one place.[Favorited Favorite](# "Add to favorites") 2[](https://learn.sparkfun.com/tutorials/spectacle-button-board-hookup-guide) [### 眼镜按钮板连接导轨](https://learn.sparkfun.com/tutorials/spectacle-button-board-hookup-guide) All the information you need to use the Spectacle Button Board in one place.[Favorited Favorite](# "Add to favorites") 2[](https://learn.sparkfun.com/tutorials/spectacle-light-board-hookup-guide) [### 眼镜灯板连接导轨](https://learn.sparkfun.com/tutorials/spectacle-light-board-hookup-guide) All the information you need to use the Spectacle Light Board in one place.[Favorited Favorite](# "Add to favorites") 2[](https://learn.sparkfun.com/tutorials/spectacle-motion-kit-hookup-guide) [### 眼镜运动套件连接指南](https://learn.sparkfun.com/tutorials/spectacle-motion-kit-hookup-guide) All the information you need to use the Spectacle Motion Kit in one place.[Favorited Favorite](# "Add to favorites") 2[](https://learn.sparkfun.com/tutorials/spectacle-motion-board-hookup-guide) [### 眼镜运动板连接指南](https://learn.sparkfun.com/tutorials/spectacle-motion-board-hookup-guide) All the information you need to use the Spectacle Motion Kit in one place.[Favorited Favorite](# "Add to favorites") 2[](https://learn.sparkfun.com/tutorials/spectacle-inertia-board-hookup-guide) [### 眼镜惯性板连接导轨](https://learn.sparkfun.com/tutorials/spectacle-inertia-board-hookup-guide) Everything you need to know about using the Spectacle Inertia Board in one place.[Favorited Favorite](# "Add to favorites") 2[](https://learn.sparkfun.com/tutorials/spectacle-example-super-mario-bros-diorama) [### 奇观例子:超级马里奥兄弟西洋镜](https://learn.sparkfun.com/tutorials/spectacle-example-super-mario-bros-diorama) A study in building an animated diorama (with sound!) using Spectacle electronics.[Favorited Favorite](# "Add to favorites") 1********