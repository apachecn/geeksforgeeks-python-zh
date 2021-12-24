# Python |如何给程序计时

> 原文:[https://www . geesforgeks . org/python-如何计时程序/](https://www.geeksforgeeks.org/python-how-to-time-the-program/)

本文旨在展示如何计算执行各种任务所需的时间。
一个简单的解决方法是使用**时间**模块。该模块包含各种与时间相关的功能。此外，在这些函数上放置一个更高级别的接口并将其用作秒表也非常有用，如下面的代码中所解释的–

**代码#1 :**

## 蟒蛇 3

```py
# Using time module
import time

# defining the class
class Timer:

def __init__(self, func = time.perf_counter):
    self.elapsed = 0.0
    self._func = func
    self._start = None

# starting the module
def start(self):
    if self._start is not None:
        raise RuntimeError('Already started')
    self._start = self._func()

# stopping the timer
def stop(self):
    if self._start is None:
        raise RuntimeError('Not started')
    end = self._func()
    self.elapsed += end - self._start
    self._start = None

# resetting the timer
def reset(self):
    self.elapsed = 0.0
    @property

def running(self):
    return self._start is not None

def __enter__(self):
    self.start()
    return self

def __exit__(self, *args):
    self.stop()
```