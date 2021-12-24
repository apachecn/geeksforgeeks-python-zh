# 使用 Python 为笔记本电脑创建电池通知程序

> 原文:[https://www . geesforgeks . org/create-battery-notifier-for-笔记本电脑-使用-python/](https://www.geeksforgeeks.org/create-battery-notifier-for-laptop-using-python/)

笔记本电脑或电池充电总是一种压力。我们经常忘记给笔记本电脑充电，似乎在检查电池。本文演示了如何使用 Python 创建一个简单的**电池通知器**应用程序。电池通知程序是一个简单的应用程序，它在桌面上以弹出消息的形式产生通知消息。借助 Python，我们可以在 psutil 库和 plyer 库的帮助下做到这一点。

#### 需要的模块

*   [**psutil(python 系统和进程实用程序):**](https://www.geeksforgeeks.org/psutil-module-in-python/) 它是一个跨平台的工具，用于检索 python 中运行的进程和系统利用率的信息

```py
pip install psutil
```

*   **普利特:** 普利特模块用于访问硬件的特性。这个模块没有内置 Python。我们需要从外部安装它。要安装此模块，请在终端中键入以下命令。

```py
pip install plyer
```

**进场:**

**步骤 1)** 从 plyer 模块导入通知类

```py
from plyer import notification
```

**步骤 2)** 之后只需要调用这个类的 notify 方法。

> ***语法:** notify(title=，message=，app_name=，app_icon=，timeout=10，ticker=，toast=False)*
> 
> ***参数:***
> 
> *   ***标题**(str)–通知标题*
> *   ***消息**(str)–通知消息*
> *   ***应用 _ 名称**(str)–发布此通知的应用名称*
> *   ***app _ Icon**(str)–与消息一起显示的图标*
> *   ***超时**(int)–显示消息的时间，默认为 10*
> *   ***跑马灯**(str)–通知到达时状态栏上显示的文本*
> *   ***吐司**(bool)–简单安卓消息代替完整通知*

**步骤 3)** 添加睡眠功能，再次显示该通知。

下面是实现。

## 蟒蛇 3

```py
import psutil
from plyer import notification
import time

# from psutil we will import the
# sensors_battery class and with
# that we have the battery remaining
while(True):
    battery = psutil.sensors_battery()
    percent = battery.percent

    notification.notify(
        title="Battery Percentage",
        message=str(percent)+"% Battery remaining",
        timeout=10
    )

    # after every 60 mins it will show the
    # battery percentage
    time.sleep(60*60)

    continue
```

**输出:**

<video class="wp-video-shortcode" id="video-471281-1" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200819193247/battery-notifier-python.webm?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200819193247/battery-notifier-python.webm](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200819193247/battery-notifier-python.webm)</video>

**注意:**睡眠功能中的时间已减少，以记录输出窗口。