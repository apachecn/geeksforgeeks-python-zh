# 更改 Kivy 中按钮的大小和位置

> 原文:[https://www . geeksforgeeks . org/更改按钮的大小和位置-in-kivy/](https://www.geeksforgeeks.org/change-the-size-and-position-of-button-in-kivy/)

Kivy 是 Python 中独立于平台的 GUI 工具。因为它可以在安卓、IOS、linux 和 Windows 等平台上运行。它基本上是用来开发安卓应用程序的，但并不意味着它不能在桌面应用程序上使用。
在本文中，我们将看到如何在 kivy Python 中更改按钮的大小和位置。有 4 个属性需要设置，按钮的*大小*和*位置*。有两个属性用于静态放置，另外两个用于动态放置。

> **大小:**需要两个参数(即宽度、高度)。
> 
> ## 蟒蛇 3
> 
> ```py
> b1 = Button(size =(100, 100))
> b2 = Button(size =(200, 200))
> ```