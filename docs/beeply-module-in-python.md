# Python 中的 Beeply 模块

> 原文:[https://www.geeksforgeeks.org/beeply-module-in-python/](https://www.geeksforgeeks.org/beeply-module-in-python/)

python 中的 *beeply* 模块将帮助您使用计算机特有的哔哔声来制作音符。完全是用 python 写的(准确的说是用 *winsound* 和 *time* 模块)

由于这个模块是用 *winsound* 编写的，所以只会在 Windows 上工作。本模块只包含一个类和一个方法，即 *beeply* 类和 *head()* 方法。

**安装:**

```py
pip install beeply
```

**以下是一些描述使用 beeply 模块的示例:**

**例 1**

音阶是音乐的音调基础。这是一组音调，从中可以产生旋律。下划线 *_* 用于声音的音阶如果给定了 *_* ，则音阶为 1

**语法**:

> obj = **音符哔哔声(**持续时间，单位为毫秒 **)**
> 
> 哔哔声是类，它的构造函数需要一个 arg(可选)的持续时间，如果没有给定，它将需要 900 毫秒
> 
> 如果给的话，确保是毫秒。
> 
> **听到(**自我，持续时间单位为毫秒 **)**

## 蟒蛇 3

```py
# import required module
from beeply.notes import *

# Creating obj of beeply
# It's has another arg of duration
# By default it's 900 ms
a = beeps()

# It's has another arg of duration
# By default it's 900 ms
a.hear('A_')

print("Done ")

# To acknowledge us
a.hear("A")
```

**输出:**

<video class="wp-video-shortcode" id="video-509464-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201105105029/Tst1.Py---Beeply---Vs-Code-1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201105105029/Tst1.Py---Beeply---Vs-Code-1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201105105029/Tst1.Py---Beeply---Vs-Code-1.mp4)</video>

它会在 1 级和 0 级产生 A 音，你可以听到 2 声哔哔声，每声 0.9 秒。

**例 2**

## 蟒蛇 3

```py
# import module
from beeply.notes import *

# create object with duration as argument
a = beeps(1154)

# It will sound for 1154 ms
a.hear('A_')

# But if it is
a.head('A_', 5000)

# Then it is for 5 sec i.e. 5000ms
print("Done")
```

**输出:**

<video class="wp-video-shortcode" id="video-509464-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201105105400/Tst2.Py---Beeply---Vs-Code--1.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20201105105400/Tst2.Py---Beeply---Vs-Code--1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201105105400/Tst2.Py---Beeply---Vs-Code--1.mp4)</video>

如果你在创建对象时(即实例化时)给出持续时间作为参数，那么如果没有特别给出，它也将是听觉功能的默认持续时间。