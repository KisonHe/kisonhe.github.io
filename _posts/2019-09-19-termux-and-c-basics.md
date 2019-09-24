---
layout: post
title: Termux 与 C 基础
tags: SMEESA tutorial termux
comment: true
---

很简单的介绍 Termux 

很多新同学想参与软件培训，但却因为没有电脑而发着愁  
我介绍了一些在线IDE， 但有时却需要稳定的国际互联网链接才能舒适使用

有没有什么功能强大，并且入门快速的，可以在手机上学习，调试 C 的软件呢？

这里向大家介绍 Termux。Termux是一个Android终端模拟器和Linux环境应用程序，可直接使用，无需root或设置。自动安装最小基本系统，使用APT包管理器可以使用其他软件包。


安装后第一次打开，会看到这样的界面。这是termux在下在一些基本文件。
如果你有稳定的互联网链接，应该能很快下载完成。如果没有，你可能需要稍作等待。
![installing](/asset/images/2019-09/termux-and-c-basics/installing.jpg)

打开以后，我们首先换一个软件源 参考网址 [termux-使用帮助](https://mirror.tuna.tsinghua.edu.cn/help/termux/) 

正如网址所说，我在我的手机上测试出现错误的可能极高，因此我们需要修改一下代码的执行顺序

```bash
sed -i 's@^\(deb.*stable main\)$@#\1\ndeb https://mirrors.tuna.tsinghua.edu.cn/termux stable main@' $PREFIX/etc/apt/sources.list
```

然后使用 **Ctrl-D** 退出 Termux  (**我强烈建议你找个英文输入法)**  
随后重新打开 Termux

PS: Ctrl-D 的输入只需要按下屏幕上的虚拟按键 Ctrl

![ctrl](/asset/images/2019-09/termux-and-c-basics/ctrl.jpg)

输入
```bash
apt update && apt upgrade
```
等待代码执行完毕后，你可以选择安装一个Text Editor

之前接触过Linux的同学可能对Vim有所耳闻，但这里我们推荐更加适合新手的nano
```bash
apt install nano clang
```

这时 g++ 与 nano 就安装完毕了

在开始写代码之前，我们还需要一个小小的操作，使我们的编程之旅更加轻松
```bash
mkdir -p ~/.termux/ && touch ~/.termux/termux.properties && echo " extra-keys = [ ['ESC','|','/','HOME','UP','END','PGUP','DEL'],  ['TAB','CTRL','ALT','LEFT','DOWN','RIGHT','PGDN','BKSP'] ]"  >> ~/.termux/termux.properties
```

然后使用 **Ctrl-D** 退出 Termux，并重新打开 Termux，这时你会看到，虚拟按键现在有方向键了

> 想要解释以上命令干了什么，需要介绍bash。但是bash命令似乎今晚写不完了，就下次再说吧。如果你感兴趣，请阅读文末拓展阅读部分


安装完毕以后，可以新建文件了

```bash
nano -w try.c
```
这条命令打开 try.c， 接下来键入你的代码
比如
```C++
#include <stdio.h>

//This Program prints "hello world!"
int main(void)
{
    printf("hello world!");

    return 0;
}

```

退出保存即可（屏幕上写了，Ctrl-X退出， 然后问你是否保存，按下 Y 则保存。最后是文件名。不加修改按下回车即可）

接下来开始编译
```bash
g++ try.c
```

这里我没有指定输出文件的名字，默认会生成 a.out 这个文件

想执行可执行文件，直接输入他的名字就好。但这里我们不能使用
```bash
a.out
```
必须输入

```bash
./a.out
```

原因超出了本文的范围，如果感兴趣，请搜索 环境变量 $PATH


接下来能看到我们希望的输出

![heloworld](/asset/images/2019-09/termux-and-c-basics/helloworld.jpg)


有学弟会可能会问，这个看起来很麻烦，我为什么不一个看起来更简单的App来练习C语言呢？
> 1：termux能做到的远远超出你的想象，你可以借此机会学习一些Linux相关的知识。本博主现在十分后悔大一的时候没有好好学Linux

> 2: 调试的时候使用 GDB, 逼着你了解更深层次的东西 

> 3: 养成看英文文档的好习惯

> 4: ~~termux界面好看~~

---

## 各类链接

> [termuxwiki](https://wiki.termux.com/wiki/Main_Page)

> [online-IDE](https://www.onlinegdb.com/online_c_compiler)

> [termux-使用帮助](https://mirror.tuna.tsinghua.edu.cn/help/termux/)

### 拓展阅读

> [Compiling with g++](https://www.geeksforgeeks.org/compiling-with-g-plus-plus/)


> [Introduction to Linux](https://www.tldp.org/LDP/intro-linux/html/)


> [Nano Basics](https://wiki.gentoo.org/wiki/Nano/Basics_Guide)

> [Vim Basics](https://www.openvim.com)



