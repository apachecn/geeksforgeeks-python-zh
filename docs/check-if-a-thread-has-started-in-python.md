# 检查 Python 中的线程是否已经启动

> 原文:[https://www . geesforgeks . org/check-if-a-thread-start-in-python/](https://www.geeksforgeeks.org/check-if-a-thread-has-started-in-python/)

**问题:**要知道一个启动的线程什么时候会真正开始运行。

线程的一个关键特征是它们独立且不确定地执行。如果程序中的其他线程在执行进一步的操作之前需要知道某个线程是否已经到达其执行的某个点，这可能会带来棘手的同步问题。要解决此类问题，请使用**线程库**中的事件对象。

事件实例类似于“粘性”标志，它允许线程等待某件事情发生。最初，事件设置为 0。如果事件未设置，线程等待该事件，它将阻塞(即进入睡眠状态)，直到事件设置完毕。设置事件的线程将唤醒所有正在等待的线程(如果有)。如果一个线程等待一个已经设置好的事件，它只是继续前进，继续执行。

**代码#1:使用事件协调线程启动的代码。**

```py
from threading import Thread, Event
import time

# Code to execute in an independent thread
def countdown(n, started_evt):
    print('countdown starting')
    started_evt.set()

    while n > 0:
        print('T-minus', n)
        n -= 1
        time.sleep(5)

# Create the event object that 
# will be used to signal startup
started_evt = Event()

# Launch the thread and pass the startup event
print('Launching countdown')
t = Thread(target = countdown, args =(10, started_evt))
t.start()

# Wait for the thread to start
started_evt.wait()
print('countdown is running')
```

运行上述代码时，“倒计时正在运行”消息将始终出现在“倒计时开始”消息之后。这由使主线程等待直到`countdown()`功能第一次打印启动消息的事件来协调。

*   事件对象最好用于一次性事件。也就是说，创建一个事件，线程等待事件被设置，一旦设置，事件就被丢弃。
*   虽然可以使用其`clear()`方法清除事件，但安全清除事件并等待其再次设置是一项棘手的协调工作，可能会导致错过事件、死锁或其他问题(特别是，不能保证在设置事件后清除事件的请求会在释放的线程循环返回再次等待事件之前执行)。
*   如果一个线程要一遍又一遍地重复发出一个事件的信号，那么最好使用条件对象。

**代码#2:实现一个周期计时器，只要计时器超时，其他线程就可以监视该计时器。**

```py
import threading
import time

class PeriodicTimer:
    def __init__(self, interval):
        self._interval = interval
        self._flag = 0
        self._cv = threading.Condition()

    def start(self):
        t = threading.Thread(target = self.run)
        t.daemon = True
        t.start()
def run(self):
    '''
    Run the timer and notify waiting threads after each interval
    '''
    while True:
        time.sleep(self._interval)
        with self._cv:
            self._flag ^= 1
            self._cv.notify_all()

def wait_for_tick(self):
    '''
    Wait for the next tick of the timer
    '''
    with self._cv:
        last_flag = self._flag
        while last_flag == self._flag:
            self._cv.wait()
```

**代码#3:定时器的使用**

```py
# Example use of the timer
ptimer = PeriodicTimer(5)
ptimer.start()

# Two threads that synchronize on the timer
def countdown(nticks):
    while nticks > 0:
        ptimer.wait_for_tick()
        print('T-minus', nticks)
        nticks -= 1

def countup(last):
    n = 0
    while n < last:
        ptimer.wait_for_tick()
        print('Counting', n)
        n += 1

threading.Thread(target = countdown, args =(10, )).start()
threading.Thread(target = countup, args =(5, )).start()
```

事件对象的一个关键特性是它们唤醒所有等待的线程。如果编写一个只需要唤醒一个等待线程的程序，最好使用 Semaphore 或 Condition 对象。

**代码#4:涉及信号量的代码**

```py
def worker(n, sema):
    # Wait to be signaled
    sema.acquire()
    # Do some work
    print('Working', n)

# Create some threads
sema = threading.Semaphore(0)
nworkers = 10

for n in range(nworkers):
    t = threading.Thread(target = worker, args =(n, sema, ))
    t.start()
```

在运行这段代码时，一个线程池将会启动，但是什么也不会发生，因为它们在等待获取信号量时都被阻塞了。每次信号量释放时，只有一个工作人员会醒来并运行，如下面的代码所示

**代码#5 :**

```py
sema.release()
sema.release()
```

**输出:**

```py
Working 0
Working 1
```

编写涉及大量线程间复杂同步的代码很可能会让你脑袋开花。更明智的方法是将线程作为使用队列的通信任务或作为参与者。