---
title: Android的USB OTG功能
date: 2017-07-25 14:42:00
tags: Android
---

Android是开源系统的集大成者，有很多很多极客玩法，很多玩法感觉就是高级黑。而OTG功能就是很大的一个亮点。OTG功能一般在TVBox上应用比较广泛，在手机上基本上会被忽略，那么Android OTG到底可以实现哪些功能呢？

1. HID设备：键盘、鼠标、触摸板、游戏手柄（需要配置）等等，Android 3.1+
2. Mass Storage存储设备： U盘，移动硬盘等，Android 3.1+
3. Audio设备：一些USB耳机，音频解码器，都是可以原生支持的, Android 5.0+
4. MTP设备：数码相机，手机(作为客户端)等等。Android 7.0+
5. USB打印机: 老的打印机仅支持USB，可以通过OTG配合APP使用。Android 3.1+
6. USB显示器/外置显卡：支持Displaylink芯片的外置显卡，配合APP使用。Android 5.0+
7. USB以太网：外界USB意外网卡，通过RJ45网线上网。Android 4.4+
8. USB MIDI：外接电音器材，例如键盘什么的. Android 6.0+
9. USB Camera：UVC免驱摄像头，配合APP支持。 Android 4.0+
10. USB 串口： 可以外接USB串口设备用于调试智能硬件等。Android 3.1+

其实还是蛮多的，基本上电脑的一些外设配件，Android都会慢慢支持了，这也是Android相比iOS的一大好处，这里面大多数类型我都有尝试过，没尝试的网上也很容易能找到资源。Android官方自从3.1.x开始支持USB Host，也就是OTG的功能，同时抽象出了USB相关操作API，android.hardware.usb，原则上，只要通过Android 提供的USB的API来开发，任何设备都可以支持.