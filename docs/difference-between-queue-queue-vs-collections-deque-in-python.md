# Python 中 queue.queue 与 collections.deque 的区别

> 原文:[https://www . geesforgeks . org/queue-queue-vs-collections-deque-in-python/](https://www.geeksforgeeks.org/difference-between-queue-queue-vs-collections-deque-in-python/)

两个 [queue.queue](https://www.geeksforgeeks.org/queue-in-python/) 和[collections . de queue](https://www.geeksforgeeks.org/deque-in-python/)命令都向读者提供了关于队列的一般概念，但是两个命令都有非常不同的应用，因此不应该混淆为一个。尽管它们是不同的，并且用于非常不同的目的，但是它们在功能上是相互联系的。在我们进入它们实际上做什么以及它们如何相互联系之前，有一个概念必须重新审视，即计算机软件处理的基础。

我们知道，任何程序都会变成一个处于活动状态的进程，每个进程都可以分解成线程，从而获得它所拥有的优势。我们还知道，两个线程可能必须相互通信，这就是 queue.queue 出现的地方。另一方面，Collections.deque 被用作线程内的数据结构来执行某些功能。它们之间的联系是 queue.queue 在内部使用 collections.deque。两者都处理线程安全操作。

**排队。队列:**如上所述，这个类用于促进来自同一个进程的两个线程之间的通信。它的工作原理就像一个典型的队列，唯一不同的是它服务的目的。它拥有[多处理.队列](https://www.geeksforgeeks.org/multiprocessing-python-set-2/#:~:text=Queue%20%3A%20A%20simple%20way%20to,a%20near%20clone%20of%20queue.)的所有功能，还有另外两个功能——task _ done()和 join()。

*   顾名思义，task_done()用于通知任务完成
*   Join()用于要求所有任务等待，直到所有进程完成处理。

## 蟒蛇 3

```
# import modules
import threading, queue

# setting up a queue for threads
q = queue.Queue()

def execute_thread():
    while True:
        th=q.get()
        print(f'task {th} started')
        print(f'task {th} finished')
        q.task_done()

# set up for threads to work
threading.Thread(target = execute_thread,
                 daemon = True).start()

# sending task requests 
for i in range(5):
    q.put(i)
print("all tasks sent")

# making threads wait until all tasks are done
q.join()
print("all tasks completed")
```

**输出:**

```
all tasks sent
task 0 started
task 0 finished
task 1 started
task 1 finished
task 2 started
task 2 finished
task 3 started
task 3 finished
task 4 started
task 4 finished
all tasks completed

```

**收藏。一种通用的数据结构，其行为类似于常规的先进先出队列。这在一个线程中用来完成一些功能。其基本实现如下所示:**

## 蟒蛇 3

```
# import module
from collections import deque

# initialise
dq = deque(['first','second','third'])
print(dq)
deque(['first', 'second', 'third'])

# adding more values
dq.append('fourth')
dq.appendleft('zeroth')
print(dq)
deque(['zeroth', 'first', 'second', 'third', 'fourth'])

# adding value to a specified index
dq.insert(0,'fifth')
print(dq)
deque(['fifth', 'zeroth', 'first', 'second', 'third', 'fourth'])

# removing values
dq.pop()
'fourth'
print(dq)
deque(['fifth', 'zeroth', 'first', 'second', 'third'])
dq.remove('zeroth')
print(dq)
deque(['fifth', 'first', 'second', 'third'])
```

**输出:**

> 德格(['第一'，'第二'，'第三'])
> 德格(['第零'，'第一'，'第二'，'第三'，'第四'])
> 德格(['第五'，'第零'，'第一'，'第二'，'第二'，'第三'])
> 德格(['第五'，'第一'，'第二'，'第三'])