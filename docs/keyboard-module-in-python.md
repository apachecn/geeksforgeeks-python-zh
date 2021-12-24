# Python 中的键盘模块

> 原文:[https://www.geeksforgeeks.org/keyboard-module-in-python/](https://www.geeksforgeeks.org/keyboard-module-in-python/)

Python 提供了一个名为`keyboard` 的库，用来获得对键盘的完全控制。这是一个小型 Python 库，可以挂钩全局事件、注册热键、模拟按键等等。

*   它有助于输入按键，记录键盘活动并阻止按键，直到输入指定的按键并模拟按键。
*   它捕获所有按键，甚至屏幕键盘事件也被捕获。
*   键盘模块支持复杂的热键。
*   使用这个模块，我们可以收听和发送键盘事件。
*   它适用于 windows 和 linux 操作系统。

使用以下命令安装:

```
pip install keyboard
```

**示例#1:**

```
# Using Keyboard module in Python
import keyboard

# It writes the content to output
keyboard.write("GEEKS FOR GEEKS\n")

# It writes the keys r, k and endofline 
keyboard.press_and_release('shift + r, shift + k, \n')
keyboard.press_and_release('R, K')

# it blocks until ctrl is pressed
keyboard.wait('Ctrl')
```

**输出:**

```
GEEKS FOR GEEKS 
RK
rk

```

**例 2:** 键盘模块输入热键。

```
# Keyboard module in Python
import keyboard

# press a to print rk
keyboard.add_hotkey('a', lambda: keyboard.write('Geek'))
keyboard.add_hotkey('ctrl + shift + a', print, args =('you entered', 'hotkey'))

keyboard.wait('esc')
```

**输出:**

```
ark
you entered hotkey

```

**例 3:** 键盘模块也用来记录所有的键盘活动，并使用 play 方法进行回放。

```
# Keyboard module in Python
import keyboard

# It records all the keys until escape is pressed
rk = keyboard.record(until ='Esc')

# It replay back the all keys
keyboard.play(rk, speed_factor = 1)
```

**输出:**

```
www.geeksforgeeks.org 

```

**参考:**[https://pypi.org/project/keyboard/](https://pypi.org/project/keyboard/)