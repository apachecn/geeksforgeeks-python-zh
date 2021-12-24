# Python |线程间通信| Set-1

> 原文:[https://www . geesforgeks . org/python-线程间通信-set-1/](https://www.geeksforgeeks.org/python-communicating-between-threads-set-1/)

给定程序中的多个线程，人们希望在它们之间安全地通信或交换数据。

也许将数据从一个线程发送到另一个线程最安全的方法是使用队列库中的队列。为此，创建一个由线程共享的队列实例。线程然后使用`put()`或`get()`操作从队列中添加或移除项目，如下文给出的代码所示。

**代码#1 :**

```py
from queue import Queue
from threading import Thread

# A thread that produces data
def producer(out_q):
    while True:
        # Produce some data
        ...
        out_q.put(data)

# A thread that consumes data
def consumer(in_q):
    while True:
        # Get some data
        data = in_q.get()
        # Process the data
        ...

# Create the shared queue and launch both threads
q = Queue()
t1 = Thread(target = consumer, args =(q, ))
t2 = Thread(target = producer, args =(q, ))
t1.start()
t2.start()
```

队列实例已经拥有所有必需的锁定，因此可以根据需要由尽可能多的线程安全地共享它们。当使用队列时，协调生产者和消费者的关闭可能有些棘手。

这个问题的一个常见解决方案是依赖一个特殊的 sentinel 值，当它被放入队列中时，会导致使用者终止，如下面的代码所示:

**代码#2 :**

```py
from queue import Queue
from threading import Thread

# Object that signals shutdown
_sentinel = object()

# A thread that produces data
def producer(out_q):
    while running:
        # Produce some data
        ...
        out_q.put(data)

    # Put the sentinel on the queue to indicate completion
    out_q.put(_sentinel)

# A thread that consumes data
def consumer(in_q):
    while True:
        # Get some data
        data = in_q.get()

        # Check for termination
        if data is _sentinel:
            in_q.put(_sentinel)
            break
        ...
```

上面代码的一个微妙特征是，消费者在收到特殊的 sentinel 值后，立即将其放回队列。这将哨兵传播给可能正在监听同一队列的其他消费者线程，从而一个接一个地关闭它们。

尽管队列是最常见的线程通信机制，但只要添加所需的锁定和同步，就可以构建自己的数据结构。最常见的方法是用条件变量包装数据结构。

**代码#3:构建线程安全的优先级队列**

```py
import heapq
import threading

class PriorityQueue:
    def __init__(self):
        self._queue = []
        self._count = 0
        self._cv = threading.Condition()

    def put(self, item, priority):
        with self._cv:
            heapq.heappush(self._queue, (-priority, self._count, item))
            self._count += 1
            self._cv.notify()

    def get(self):
        with self._cv:
            while len(self._queue) == 0:
                self._cv.wait()
            return heapq.heappop(self._queue)[-1]
```

与队列的线程通信是一个单向且不确定的过程。一般来说，没有办法知道接收线程实际上是什么时候收到消息并处理它的。然而，队列对象确实提供了一些基本的完成特性，如下面给出的例子中的`task_done()`和`join()`方法所示

**代码#4 :**

```py
from queue import Queue
from threading import Thread

# A thread that produces data
def producer(out_q):
    while running:
        # Produce some data
        ...
        out_q.put(data)

# A thread that consumes data
def consumer(in_q):
    while True:
        # Get some data
        data = in_q.get()
        # Process the data
        ...
        # Indicate completion
        in_q.task_done()

# Create the shared queue and launch both threads
q = Queue()
t1 = Thread(target = consumer, args =(q, ))
t2 = Thread(target = producer, args =(q, ))
t1.start()
t2.start()

# Wait for all produced items to be consumed
q.join()
```