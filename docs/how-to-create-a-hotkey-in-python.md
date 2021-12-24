# 如何在 Python 中创建热键？

> 原文:[https://www . geesforgeks . org/如何在 python 中创建热键/](https://www.geeksforgeeks.org/how-to-create-a-hotkey-in-python/)

这篇文章是关于如何使用 Python 创建一个热键。但是首先，让我们讨论什么是热键。热键是一个指定的键或键序列，用于在软件应用程序中执行命令或执行选定的任务:例如，在 Windows 计算机上，热键 Ctrl+S 通常不能快速保存文件。

通过将这样的序列减少到几个击键，通常可以节省用户时间，因此“快捷”并使残疾人的计算更加容易。

**方法 1:** 使用 pynput(此库允许您控制和监控输入设备。)

**采用的方法:**

1.  我们从 pynput 进口键盘
2.  然后，我们创建一个集合来跟踪当前按下了哪些键输入
3.  创建需要按下哪个热键来执行所需操作的列表。这里我们希望热键是 Shift+a 和 Shift+A
4.  我们创建一个函数 execute()，在按热键的同时运行我们想要的程序。在这里，我们希望打印“检测热键”
5.  创建一个 on_press()函数，检查在给定条件下按下的任何键。如果是，我们需要添加到集合中，然后查看所有键和特定组合是否都在当前集合中。如果是，我们就执行我们的操作。
6.  创建一个 on_release()函数，检查在给定的组合下释放的任何键。如果是，我们需要将其从当前集合中移除。
7.  最后，运行程序。

## 蟒蛇 3

```py
from pynput import keyboard

cmb = [{keyboard.Key.shift, keyboard.Key(char='a')},{keyboard.Key.shift, keyboard.Key(char='A')}]

current = set()

def execute():
  print("Detected hotkey")

def on_press(key):
  if any([key in z for z in cmb]):
    current.add(key)
    if any(all(k in current for k in z) for z in cmb):
      execute()

def on_release(key):
  if any([key in z for z in cmb]):
    current.remove(key)

with keyboard.Listener(on_press=on_press, on_release=on_release) as listener:
  listener.join()
```

**输出:**

![](img/da276b63681c312fff22d7781aa4d6c0.png)

**方法二:** 使用键盘(参考文章:[Python 中的键盘模块)](https://www.geeksforgeeks.org/keyboard-module-in-python/)

Python 提供了一个名为 keyboard 的库，用来促进对键盘的完全控制。这是一个小的 Python 库，可以挂钩全局事件、注册热键、模拟按键等等。

*   它有助于输入按键，记录键盘活动并阻止按键，直到输入指定的按键并模拟按键。
*   它捕获所有按键，甚至屏幕键盘事件也被捕获。
*   键盘模块支持复杂的热键。
*   使用本模块，我们将监听并发送键盘事件。，它在 Windows 和 Linux 操作系统上都可以工作。

## 蟒蛇 3

```py
# Keyboard module in Python 
import keyboard 

# press ctrl+shift+z to print "Hotkey Detected" 
keyboard.add_hotkey('ctrl + shift + z', print, args =('Hotkey', 'Detected')) 

keyboard.wait('esc') 
```

**输出:**

```py
Hotkey Detected
```