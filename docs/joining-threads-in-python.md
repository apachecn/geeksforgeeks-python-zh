# 在 Python 中连接线程

> 原文:[https://www.geeksforgeeks.org/joining-threads-in-python/](https://www.geeksforgeeks.org/joining-threads-in-python/)

像同时运行多个独立程序一样，同时运行**多个线程**也有类似的特性，并有一些额外的好处，具体如下:

*   在一个进程中，多个线程与主线程共享相同的数据空间。因此，它们可以很容易地共享信息或相互通信，而不像进程那样。
*   也被称为**轻量进程**，它们需要更少的内存开销，因此比进程更便宜。

**多线程**定义为同时或并发执行多个线程的能力。因此，一个进程中可能存在多个线程，其中:

*   每个线程的**寄存器组**和**局部变量**存储在堆栈中。
*   所有线程共享**全局变量**(存储在堆中)和**程序代码**。

## 连接螺纹的方法

在调用 **join()** 方法时，调用线程被阻塞，直到线程对象(在其上调用线程)被终止。线程对象可以在以下任何一种情况下终止:

*   要么正常。
*   通过一个处理不当的异常。
*   直到可选的超时发生。

因此 join()方法指示等待，直到线程终止。我们还可以为 join()方法指定一个超时值。在这种情况下，调用线程可以通过事件对象发送信号来请求线程停止。join()方法可以多次调用。

**语法:**

```
object_name.join()
OR
object_name.join(timeout) 
where timeout argument is the timeout value.

```

**示例:**

## 蟒蛇 3

```
from threading import Thread
from threading import Event
import time

class Connection(Thread):

    StopEvent = 0

    def __init__(self,args):
        Thread.__init__(self)
        self.StopEvent = args

    # The run method is overridden to define 
    # the thread body 
    def run(self):

        for i in range(1,10):
            if(self.StopEvent.wait(0)):
                print ("Asked to stop")
                break;

            print("The Child Thread sleep count is %d"%(i))
            time.sleep(3)

        print ("A Child Thread is exiting")

Stop = Event()
Connection = Connection(Stop)           
Connection.start()
print("Main thread is starting to wait for 5 seconds")

Connection.join(5) 
print("Main thread says : I cant't wait for more than 5 \
seconds for the child thread;\n Will ask child thread to stop")

# ask(signal) the child thread to stop
Stop.set()

# wait for the child thread to stop
Connection.join()

print("Main thread says : Now I do something else to compensate\
the child thread task and exit")
print("Main thread is exiting")
```

**输出:**

> 子线程睡眠计数为 1
> 主线程开始等待 5 秒
> 子线程睡眠计数为 2
> 主线程说:我不能再等子线程超过 5 秒了；
> 会要求子线程停止
> 要求停止
> 一个子线程正在退出
> 主线程说:现在我做点别的来补偿子线程任务，退出
> 主线程正在退出

**使用 Python 中的 join()连接线程时需要记住的要点:**

*   当在同一线程上调用 join()方法时会发生运行时错误，因为在同一线程上调用 join()会导致死锁情况。
*   如果在尚未启动的线程上调用 join()方法，则会引发运行时错误。
*   如果 join()有超时参数，那么它应该是一个浮点数，以秒为单位表示线程操作的时间。
*   如果 join()方法没有参数，则阻塞直到线程终止操作。
*   由于 join()返回的值始终是 None，所以我们应该总是在 join()之后立即使用 isAlive()来检查线程是否还活着。