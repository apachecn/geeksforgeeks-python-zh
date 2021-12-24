# Python |杀死线程的不同方法

> 原文:[https://www . geeksforgeeks . org/python-不同的线程终止方式/](https://www.geeksforgeeks.org/python-different-ways-to-kill-a-thread/)

一般来说，突然终止线程被认为是一种糟糕的编程实践。突然终止一个线程可能会留下一个必须正确关闭、打开的关键资源。但是一旦某个特定的时间段过去或者某个中断已经生成，您可能想要终止一个线程。python 中有多种方法可以杀死线程。

*   在 python 线程中引发异常
*   设置/重置停止标志
*   使用跟踪来终止线程
*   使用多处理模块杀死线程
*   通过将 Python 线程设置为守护进程来杀死它
*   使用隐藏函数 stop()

**在 python 线程中引发异常:**
该方法使用函数[python readstate _ SetAsyncExc()](https://docs.python.org/3/c-api/init.html?highlight=pythreadstate_setasyncexc#c.PyThreadState_SetAsyncExc)在 a 线程中引发异常。例如

## 蟒蛇 3

```py
# Python program raising
# exceptions in a python
# thread

import threading
import ctypes
import time

class thread_with_exception(threading.Thread):
    def __init__(self, name):
        threading.Thread.__init__(self)
        self.name = name

    def run(self):

        # target function of the thread class
        try:
            while True:
                print('running ' + self.name)
        finally:
            print('ended')

    def get_id(self):

        # returns id of the respective thread
        if hasattr(self, '_thread_id'):
            return self._thread_id
        for id, thread in threading._active.items():
            if thread is self:
                return id

    def raise_exception(self):
        thread_id = self.get_id()
        res = ctypes.pythonapi.PyThreadState_SetAsyncExc(thread_id,
              ctypes.py_object(SystemExit))
        if res > 1:
            ctypes.pythonapi.PyThreadState_SetAsyncExc(thread_id, 0)
            print('Exception raise failure')

t1 = thread_with_exception('Thread 1')
t1.start()
time.sleep(2)
t1.raise_exception()
t1.join()
```