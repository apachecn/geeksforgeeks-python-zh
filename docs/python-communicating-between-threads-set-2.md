# Python |线程间通信| Set-2

> 原文:[https://www . geesforgeks . org/python-线程间通信-set-2/](https://www.geeksforgeeks.org/python-communicating-between-threads-set-2/)

**先决条件:** [线程间通信| Set-1](https://www.geeksforgeeks.org/python-communicating-between-threads-set-1/)

如果一个线程需要立即知道消费者线程何时处理了一个特定的数据项，那么应该将发送的数据与一个 Event 对象进行配对，这样生产者就可以监控它的进度，如下面给出的代码所示–

**Code #1 :**

```py
from queue import Queue
from threading import Thread, Event

# A thread that produces data
def producer(out_q):
    while running:
        # Produce some data
        ...
        # Make an (data, event) pair and 
        # hand it to the consumer
        evt = Event()
        out_q.put((data, evt))
        ...
        # Wait for the consumer to process the item
        evt.wait()

    # A thread that consumes data
    def consumer(in_q):
        while True:
            # Get some data
            data, evt = in_q.get()
            # Process the data
            ...
            # Indicate completion
            evt.set()
```

基于简单排队编写线程程序通常是保持理智的好方法。如果一切都分解成简单的线程安全队列，它就不需要在程序中乱丢锁和其他低级同步。此外，与队列通信通常会导致设计可以在以后扩展到其他类型的基于消息的通信模式。例如，可以将程序分成多个进程，甚至是一个分布式系统，而不需要改变它的底层排队体系结构。
线程队列的一个注意事项是，将一个项目放入队列不会复制该项目。因此，通信实际上涉及在线程之间传递对象引用。

如果担心共享状态，只传递不可变的数据结构(例如，整数、字符串或元组)或者对排队的项目进行深度复制可能是有意义的，如下面给出的代码所示:

**代码#2 :**

```py
from queue import Queue
from threading import Thread
import copy

# A thread that produces data
def producer(out_q):
    while True:
        # Produce some data
        ...
        out_q.put(copy.deepcopy(data))

# A thread that consumes data
def consumer(in_q):
    while True:
        # Get some data
        data = in_q.get()
        # Process the data
        ...
```

*   队列对象提供了一些额外的特性，这些特性在特定的环境中可能会很有用。
*   如果创建一个具有可选大小的队列，如队列(N)，它会限制在`put()`阻塞生成器之前可以排队的项目数量。
*   如果生产者和消费者之间的速度不匹配，向队列添加上限可能是有意义的。
*   例如，如果生产者生产物品的速度比消费物品的速度快得多。
*   另一方面，当队列块已满时，它也会在整个程序中产生意想不到的级联效应，可能导致死锁或运行不良。
*   一般来说，通信线程之间的“流量控制”问题比看起来要困难得多。
*   如果曾经试图通过篡改队列大小来解决问题，这可能是脆弱设计或其他一些固有的扩展问题的迹象。

**代码#3 : `get()`和`put()`支持非阻塞和超时的方法。**

```py
import queue
q = queue.Queue()

try:
    data = q.get(block = False)
except queue.Empty:
    ...
try:
    q.put(item, block = False)
except queue.Full:
    ...

try:
    data = q.get(timeout = 5.0)
except queue.Empty:
    ...
```

这两个选项都可以用来避免在特定的排队操作中无限期阻塞的问题。例如，一个非阻塞`put()`可以和一个固定大小的队列一起使用，以实现不同类型的处理代码，用于队列满的时候。

**代码# 4:发出日志消息并丢弃**

```py
def producer(q):
    ...
    try:
        q.put(item, block = False)
    except queue.Full:
        log.warning('queued item % r discarded !', item)
```

如果试图让使用者线程周期性地放弃像 `q.get()`这样的操作，以便检查像终止标志这样的东西，那么超时是有用的。

**代码#5:使用超时**

```py
_running = True

def consumer(q):
    while _running:
        try:
            item = q.get(timeout = 5.0)
            # Process item
            ...
        except queue.Empty:
            pass
```

最后，还有实用方法`q.qsize()`、`q.full()`、`q.empty()`可以告诉当前队列的大小和状态。但是，请注意，所有这些在多线程环境中都是不可靠的。例如，对 `q.empty()`的调用可能会告诉我们队列是空的，但是在调用后的这段时间里，另一个线程可能已经向队列中添加了一个项目。坦率地说，编写代码最好不要依赖这样的函数。