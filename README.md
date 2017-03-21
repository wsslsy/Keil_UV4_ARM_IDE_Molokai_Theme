# 为 Keil 更换 Sublime Text Molokai 主题
> 用户界面是第一生产力。 [@Tony_the_geek](http://weibo.com/724123001)

作为一个STM32或是其他ARM阵营MCU的开发者，我们对KEIL，或者说MDK，或者说UV4/5，应该很熟悉了。亲切的界面，即使再简洁，也总会有视觉疲劳的时候。

Sublime Text 3是一款专用于提升开发效率的文本编辑器。经过笔者长期的使用体验，其默认主题`Molokai`，是很适合长时间代码编写的。笔者认为该主题具有如下优点：
- 暗系色调，更加护眼，使使用者更加专注
- 语法高亮支持好，色调分明
- 配备微软雅黑以及`Consolas`字体，更舒适

无奈，Keil软件并不支持外嵌文本编辑器，因此，我们想改变Keil软件的外观，只能通过修改其颜色配置文件来实现。

## 准备工作
#### 操作环境：
- 系统：Windows
- 软件：Keil MDK UV4/5 for ARM
~其他版本支持不详，有待验证反馈~

#### 下载主题修改文件
[百度网盘链接](http://pan.baidu.com/s/1qYu9x4w)

#### 备份默认主题文件
首先找到Keil安装目录（以下以此安装目录为例）：`D:\Software\Keil`
可以看到，目录下存在如下几个文件夹/文件：
- `ARM\`
- `Eclipse\`
- `UV4\`
- `TOOLS.INI`
- `Uninstall.exe`

*P.S. 例子为UV4，UV5有所不同，但接下来操作相同*

打开`UV4`文件夹，找到如下文件：
- `arm.prop`
- `global.prop`
- `global.prop.def`

将这三个文件拖到其他位置，或修改其拓展名为任意（比如*.bak），防止修改失败后不能恢复。

*P.S. 如果只找到`global.prop.def`文件，说明你还未修改过默认字体等设置，将`global.prop.def`文件备份就好，不会影响接下来的操作。*

## 开始操作
#### 安装`微软雅黑 Consolas Hybrid`字体
解压主题修改压缩文件
发现其中包含文件名为：`MSYHMONO.ttf`的字体文件
找到系统字体存放目录，一般为`C:\Windows\Fonts`
将字体文件拖入该文件夹，弹出安装字体提示，确认
**至此，`微软雅黑 Consolas Hybrid`已经成功安装如你的系统**

#### 替换主题文件
复制下载的压缩包中剩余的三个文件：
- `arm.prop`
- `global.prop`
- `global.prop.def`

找到之前备份过该三文件的位置，即`UV4`文件夹，将三者粘贴在其中

## 完成
你可以开始享受 Molokai 主题的 Keil IDE 了。

![image](https://github.com/wsslsy/Keil_UV4_ARM_IDE_Molokai_Theme/blob/master/Molokai%20for%20Keil.png)

## 一些问题
由于Keil的语法高亮支持不完备，所以笔者修改了`arm.prop`中的用户关键词以及`global.prop.def`中的默认C语言关键词，同时很贴心的添加了`野火STM32库`中一些关键字的支持。注意到Keil IDE其实连像`printf();`这样的函数都没有高亮支持，没忍住强迫症，把类似这样的函数名全给高亮了。但是毕竟会有疏忽之处，希望使用主题的大家也能给我提出改进意见和建议。有之前按照自己习惯设置关键词的用户，也请提前做好备份，以免数据丢失。
**另：请勿随意改动该三文件内容，以免软件不能正常工作。**
