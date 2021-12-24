# Python:Lock 和 Rlock 对象的区别

> 原文:[https://www . geeksforgeeks . org/python-锁与锁对象的区别/](https://www.geeksforgeeks.org/python-difference-between-lock-and-rlock-objects/)

线程是进程中可被调度执行的实体。此外，它是可以在操作系统中执行的最小处理单元。简单来说，线程是程序中的一系列指令，可以独立于其他代码执行。为了简单起见，您可以假设一个线程只是一个进程的子集！

> **参考下面的文章，获得关于线程的想法。**
> 
> *   [Python 中的多线程](http://geeksforgeeks.org/multithreading-python-set-1/)

## 锁

这些是 Python 中最简单的同步原语。锁有两种状态，即**锁定和**解锁。锁是线程模块中的一个类，它的对象是在解锁状态下生成的，有两个主要方法，即`acquire()`和`release()`。当调用 acquire()方法时，它会锁定 Lock 的执行，并阻止其执行，直到在其他线程中调用 release()方法，从而将其设置为解锁状态。锁帮助我们有效地访问程序中的共享资源，以防止数据损坏，它遵循互斥，因为一次只有一个线程可以访问特定的资源。

让我们看下面的例子来理解锁的使用:

```
# program to illustrate the use of Locks

import threading

# creating a Lock object
lock = threading.Lock()

# initializing the shared resource
geek = 0

def sumOne():
       global geek

       # locking the shared resource
       lock.acquire()
       geek = geek + 1

       # unlocking the shared resource
       lock.release()

def sumTwo():
       global geek

       # locking the shared resource
       lock.acquire()
       geek = geek + 2

       # unlocking the shared resource 
       lock.release()

# calling the functions
sumOne()
sumTwo()

# displaying the value of shared resource
print(geek)
```

**输出:**

```
3
```

在上面的程序中，`lock`是 Lock 对象，全局变量`geek`是共享资源，`sumOne()`和`sumTwo()`函数充当线程，在`sumOne()`函数中，共享资源`geek`先被锁定，然后递增 1，然后释放`geek`，在`sumTwo()`函数中，变量`geek`先被锁定，然后递增 2，然后释放`geek`。两个功能`sumOne()`和`sumTwo()`不能同时访问共享资源`geek`，一次只能有一个功能访问共享资源`geek`。

## 阻碍

默认锁不识别锁当前持有的线程。如果共享资源正被任何线程访问，那么试图访问共享资源的其他线程将被阻止，即使锁定共享资源的是同一个线程。可重入锁或 RLock 在这些情况下用于防止不希望的阻塞访问共享资源。如果共享资源处于 RLock 中，则可以安全地再次调用它。RLocked 资源可以被不同的线程重复访问，尽管当被不同的线程调用时它仍然可以正常工作。

让我们看下面的例子来理解 RLocks 的使用:

```
import threading

# initializing the shared resource
geek = 0

# creating a Lock object 
lock = threading.Lock()

# the below thread is accessing the
# shared resource
lock.acquire()
geek = geek + 1

# This thread will be blocked
lock.acquire() 
geek = geek + 2
lock.release()

# displaying the value of shared resource
print(geek)
```

在上面的程序中，两个线程试图同时访问共享资源`geek`，这里当一个线程当前正在访问共享资源`geek`时，另一个线程将被阻止访问它。当两个或多个线程试图访问同一资源时，会有效地阻止对方访问该资源，这就是所谓的死锁，由于死锁，上述程序不会生成任何输出。

然而，程序中的上述问题可以通过使用 RLock 来解决。

```
# program to illustrate the use of RLocks

# importing the module
import threading

# initializing the shared resource
geek = 0

# creating an RLock object instead 
# of Lock object 
lock = threading.RLock()

# the below thread is trying to access 
# the shared resource
lock.acquire()
geek = geek + 1

# the below thread is trying to access 
# the shared resource 
lock.acquire() 
geek = geek + 2
lock.release()
lock.release()

# displaying the value of shared resource
print(geek)
```

**输出:**

```
3
```

在这里，没有不必要的阻止程序中的线程访问共享资源极客。我们需要为 RLock 对象锁的每个`acquire()`调用一次`release()`。

从上面提到的众多程序和解释来看，Python 中的 Lock 对象和 RLock 对象有许多不同之处:

| 锁 | 阻碍 |
| --- | --- |
| 锁定对象不能被任何线程再次获取，除非它被访问共享资源的线程释放。 | 任何线程都可以多次获取一个 RLock 对象。 |
| 任何线程都可以释放锁定对象。 | RLock 对象只能由获取它的线程释放。 |
| 锁定对象不能归任何人所有 | 一个 RLock 对象可以被许多线程拥有 |
| 锁定对象的执行速度更快。 | RLock 对象的执行速度比 Lock 对象慢 |