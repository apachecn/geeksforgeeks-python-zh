# 创建日期选择器日历–Tkinter

> 原文:[https://www . geesforgeks . org/create-a-date-picker-calendar-tkinter/](https://www.geeksforgeeks.org/create-a-date-picker-calendar-tkinter/)

**先决条件:**[Tkit](https://www.geeksforgeeks.org/python-gui-tkinter/)

Python 为开发图形用户界面提供了多种选择。在所有的 GUI 方法中，Tkinter 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。Python 搭配 Tkinter 是创建 GUI 应用程序最快最简单的方法。在本文中，我们将学习如何在 Tkinter 中创建日期选择器日历。

在 Tkinter 中，日期选择器日历没有内置的方法，这里我们将使用 **tkcalendar** 模块。

**tkcalendar:** tkcalendar 是一个 Python 模块，为 Tkinter 提供了 calendar 和 DateEntry 小部件。

要进行安装，请在您的终端上运行以下命令:

```
pip install tkcalendar
```

**进场:**

*   首先，我们将导入所需的库
*   然后我们将创建一个**日历对象**并传递默认日期
*   从日历中选择年、月和日期
*   要获取所选日期值的值，请使用 **get()** 方法。

> **语法:**日历(主=无，**kw)
> 
> **年份:**国际代码区块
> 
> *   它最初显示年份，默认是当前年份。
> 
> **月:** int
> 
> *   最初显示的月份，默认为当前月份。
> 
> **日:** int
> 
> *   初始选择日，如果给出月或年但不是日，则没有初始选择，否则，默认为今天。

**下面是实现:-**

## 蟒蛇 3

```
# Import Required Library
from tkinter import *
from tkcalendar import Calendar

# Create Object
root = Tk()

# Set geometry
root.geometry("400x400")

# Add Calendar
cal = Calendar(root, selectmode = 'day',
               year = 2020, month = 5,
               day = 22)

cal.pack(pady = 20)

def grad_date():
    date.config(text = "Selected Date is: " + cal.get_date())

# Add Button and Label
Button(root, text = "Get Date",
       command = grad_date).pack(pady = 20)

date = Label(root, text = "")
date.pack(pady = 20)

# Execute Tkinter
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-544807-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210117194936/FreeOnlineScreenRecorderProject1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210117194936/FreeOnlineScreenRecorderProject1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210117194936/FreeOnlineScreenRecorderProject1.mp4)</video>