# 如何从 Python 应用程序打开火狐浏览器中的 URL？

> 原文:[https://www . geeksforgeeks . org/如何在 firefox 中打开 URL-浏览器-来自 python-application/](https://www.geeksforgeeks.org/how-to-open-url-in-firefox-browser-from-python-application/)

在本文中，我们将了解如何使用 Python 应用程序来访问火狐浏览器中的网址。

为此，我们将使用**网络浏览器** Python 模块。我们不必安装它，因为它是预装的。本模块中还预定义了多种浏览器，在本文中，我们将使用**火狐**。Python 中的**网络浏览器**模块是一个有用的网络浏览器控制器。它有一个高级界面，允许用户查看基于网络的文档。

**网络浏览器**也可以作为命令行界面使用。它以一个 URL 作为参数，并添加以下参数作为选项:如果可行， **-n** 在新的浏览器窗口中打开该 URL， **-t** 在新的浏览器选项卡中打开该 URL。

## 方法:

*   我们将从导入**网络浏览器**模块开始，该模块预装，不需要额外安装。
*   我们将获取用户想要在火狐中打开的网址，并将其保存在一个变量中。如果您只想打开一个特定的网址，您可以通过在变量中预先定义网址来跳过这一步。
*   现在我们将创建一个 **Mozilla 类**的实例，它是网络浏览器模块内部的一个预定义类，并将火狐从安装目录中的可执行路径作为参数传递。火狐的可执行路径可以通过在桌面上右键单击它的快捷方式并选择属性来获得。在“快捷方式”选项卡下，查找目标标题，可执行路径就在它旁边。您也可以在安装目录中手动搜索 firefox.exe 并复制位置。
*   现在我们将使用 Mozilla 类中定义的 **open()** 函数在指定的浏览器中显示网址，如果没有指定，则显示默认浏览器。在我们的例子中，我们已经将它定义为火狐。其他功能，如在新标签中打开网址，可以在[这个](https://docs.python.org/3/library/webbrowser.html)官方文档中找到。

### 下面是实现:

## 蟒蛇 3

```
# This code is used to open URL in firefox 
# browser

import webbrowser

# To take the URL as input from the user.
print('Enter the URL: ', end="")
link = input()

# Passing firefox executable path to the
# Mozilla class.
firefox = webbrowser.Mozilla("C:\\Program Files\
\Mozilla Firefox\\firefox.exe")

# Using open() function to display the URL.
firefox.open(link)
```

**输出:**

<video class="wp-video-shortcode" id="video-715254-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20211116012221/openURL.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20211116012221/openURL.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20211116012221/openURL.mp4)</video>