# Python |如何锁定关键部分

> 原文:[https://www . geesforgeks . org/python-如何锁定关键部分/](https://www.geeksforgeeks.org/python-how-to-lock-critical-sections/)

本文的目标是如何锁定给定程序中的线程和关键部分，以避免竞争条件。所以，在*线程库中*使用 Lock 对象，让可变对象可以安全地被多个线程使用。

**代码#1 :**

```py
import threading

class counter_share:
    '''
    multiple threads can share.
    '''
    def __init__(self, initial_key = 0):
        self._key = initial_key
        self._key_lock = threading.Lock()

    def incr(self, delta = 1):
        with self._key_lock:
            # Increasing the counter with lock
            self._key += delta

    def decr(self, delta = 1):
        with self._key_lock:
            # Decreasing the counter with lock
            self._key -= delta
```

将带有语句的**与**锁一起使用**可确保互斥。排除意味着一次只允许一个线程(在 with 语句下)执行语句块。
获取预期语句持续时间的锁，并在控制流退出缩进块时释放。线程调度本质上是不确定的。因此，随机损坏的数据和“竞争条件”可能会导致无法使用锁。因此，每当共享的可变状态被多个线程访问时，应该总是使用锁来避免这种情况。**

在较旧的 Python 代码中，通常会看到锁被显式获取和释放。

**代码#2:代码 1 的变体**

```py
import threading

class counter_share:
    # multiple threads can share counter objects
    def __init__(self, initial_key = 0):
        self._key = initial_key
        self._key_lock = threading.Lock()

    def incr(self, delta = 1):
        # Increasing the counter with lock
        self._key_lock.acquire()
        self._key += delta
        self._key_lock.release()

    def decr(self, delta = 1):
        # Decreasing the counter with lock
        self._key_lock.acquire()
        self._key -= delta
        self._key_lock.release()
```

*   在不调用`release()`方法的情况下，或者在持有锁时没有引发异常的情况下，带有语句的**更不容易出错。**
*   程序中的每个线程不允许一次获取一个锁，这可能会避免死锁的情况。如果不可能，在程序中引入更高级的死锁避免。
*   同步原语，如 RLock 和 Semaphore 对象，可以在线程库中找到。

除了简单的模块锁定，还有一些更特殊的目的正在解决:

*   RLock 或可重入锁对象是同一线程可以多次获取的锁。
*   它主要在锁定或同步的基础上实现代码，这种结构被称为“监视器”在持有锁的情况下，这种类型的锁只允许一个线程使用整个函数或类的方法。

**代码#3:实现 SharedCounter 类。**

```py
import threading

class counter_share:
    # multiple threads can share counter objects
    _lock = threading.RLock()

    def __init__(self, initial_key = 0):
        self._key = initial_key

    def incr(self, delta = 1):
        # Increasing the counter with lock
        with SharedCounter._lock:
            self._key += delta

    def decr(self, delta = 1):
        # Decreasing the counter with lock
        with SharedCounter._lock:
            self.incr(-delta)
```

*   锁意味着同步类的方法，尽管锁被绑定到每个实例的可变状态。
*   在这个代码变体中，只有一个类级别的锁被该类的所有实例共享。
*   确保一次只允许一个线程使用类的方法。
*   如果已经有锁，方法调用其他也使用锁的方法是可以的。(例如`decr()`方法)。
*   如果有大量的计数器，它会更节省内存。但是，在使用大量线程并频繁更新计数器的程序中，这可能会导致更多的锁争用。

信号量项是依赖于相互计数器的同步原油。随着方块的结束，计数器增加。如果计数器为零，则前进受阻，直到计数器增加另一个字符串。如果计数器不为零，with 解释会递减计数，并允许一个字符串继续。
信号量项目不再是简单的锁定，而是对应用程序越来越有价值，包括字符串之间的移动或节流。尽管信号量可以以类似于标准锁的方式使用，但是使用中额外的多面性会反过来影响执行。

**代码#4:要限制一部分代码的并发量，请使用信号量。**

```py
from threading import Semaphore
import urllib.request

# five threads are allowed to run at once (at max)
_fetch_url_sema = Semaphore(5)

def fetch_url(url):
    with _fetch_url_sema:
        return urllib.request.urlopen(url)
```