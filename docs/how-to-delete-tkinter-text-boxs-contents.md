# 如何删除 Tkinter 文本框的内容？

> 原文:[https://www . geesforgeks . org/how-delete-tkinter-text-boxs-contents/](https://www.geeksforgeeks.org/how-to-delete-tkinter-text-boxs-contents/)

**先决条件:**

*   [python GUI–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)
*   [文本小部件](https://www.geeksforgeeks.org/python-tkinter-text-widget/)

Python 为开发图形用户界面提供了多种选择，其中 Tkinter 是最受欢迎的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。Python 结合 Tkinter 是创建所需 GUI 应用程序的最快、最可靠和最简单的方法。

## **什么是文本小部件？**

文本小部件用于在 Python 应用程序上显示文本数据。但是，Tkinter 支持可用于实现单行文本框的 Entry 小部件。但是，文本小部件可以用来显示具有各种样式和属性的多行格式文本。

### 方法

*   导入模块
*   创建一个普通的 Tkinter 窗口。
*   添加文本框

**语法:**

```py
Text(Object Name, **attr)
```

*   对于从文本框中删除内容，我们将创建一个删除按钮来实现删除方法。点击此按钮将删除文本框中的内容。

**语法:**

```py
Object_name.delete(first=number, last=number)
```

下面给出了实现相同功能的程序:

## 蟒蛇 3

```py
# Import Module
from tkinter import *

# Create Object
root = Tk()

# specify size of window.
root.geometry("400x500")

# delete content from Text Box

def delete_text():
    T.delete("1.0", "end")

# Create text widget
T = Text(root)
T.pack()

# Create Delete Button
Button(root, text="Delete", command=delete_text).pack()

# Execute Tkinter
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-522822-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201203184322/FreeOnlineScreenRecorderProject1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201203184322/FreeOnlineScreenRecorderProject1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201203184322/FreeOnlineScreenRecorderProject1.mp4)</video>