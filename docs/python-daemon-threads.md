# Python 守护线程

> 原文:[https://www.geeksforgeeks.org/python-daemon-threads/](https://www.geeksforgeeks.org/python-daemon-threads/)

总是在后台运行的线程为主线程或非后台线程提供支持，这些后台执行线程被认为是**后台线程。****守护线程**不阻止主线程退出，继续在后台运行。本文基于 python 中的线程，这里我们用例子讨论守护线程。

守护线程最好的例子之一是**垃圾收集器**，因为我们假设主线程正在执行或运行，此时出现任何内存问题，python 虚拟机(PVM)将立即执行**垃圾收集器**。****垃圾收集器**将在后台执行，销毁所有无用的对象，然后默认提供空闲内存，一旦有空闲内存可用，那么主线程将毫无问题地执行。**

## **普通线程学习非守护线程的流程**

**这个例子简化了一个非守护线程的流程，我们已经创建了一个 **thread_1()** name 函数，该函数有几行指令要执行，这些指令揭示了当主线程终止时非守护线程是如何执行的。接下来我们已经创建了函数 **thread_1()** 的线程 **T** ，这个线程目前被认为是非活动线程，现在我们启动线程 T，我们也暂时停止了主线程的执行 5 秒钟。在这 5 秒之间。线程 **T** 继续执行，当主线程将在 5 秒后执行时。其中它停止工作，但是有一个线程 **T** 仍然在执行，因为它是非守护线程，并且执行它们的指令直到它们完成。**

****下面是实现:****

## **蟒蛇 3**

```
# import module
from threading import *
import time

# creating a function
def thread_1():                
  for i in range(5):
    print('this is non-daemon thread')
    time.sleep(2)

# creating a thread T
T = Thread(target=thread_1)

# starting of thread T
T.start()     

# main thread stop execution till 5 sec.
time.sleep(5)                  
print('main Thread execution')
```

****输出:****

```
this is non-daemon thread
this is non-daemon thread
this is non-daemon thread
main Thread execution
this is non-daemon thread
this is non-daemon thread
```

## **守护线程在非守护线程上的流动**

**这是一个示例，展示了在程序执行期间守护线程如何在非守护线程上运行。在上面的例子中，我们已经看到了非守护线程是如何在主线程终止后完成其执行的，但这里有所不同。在这个例子中，我们已经创建了一个函数 **thread_1()** 和线程 **T** 与上面的例子相同，但是这里在创建了线程 **T** 之后，我们使用 **setDaemon()** 方法将线程 **T** 的非守护性质更改为守护性质，然后我们启动线程 **T** 并临时停止主线程的执行。这里有一个扭曲，当主线程完成它们的执行并终止，然后线程 **T** 也终止，因为这是一个守护线程，守护线程在主线程终止时终止它的执行，它的工作是支持主线程，如果没有主线程剩余，为什么运行在那里的守护线程也会终止，仍然执行剩余的指令。**

****下面是实现:****

## **蟒蛇 3**

```
# import modules
from threading import *
import time

# creating a function
def thread_1():                     
  for i in range(5):
    print('this is thread T')
    time.sleep(3)

# creating a thread
T = Thread(target = thread_1)

# change T to daemon
T.setDaemon(True)                  

# starting of Thread T
T.start()                          
time.sleep(5)
print('this is Main Thread') 
```

****输出:****

```
this is thread T
this is thread T
this is Main Thread
```

## ****检查线程是守护进程还是**非守护进程的方法**

****有一个方法和一个属性可以检查以下线程的性质:****

*   **isDaemon()**
*   **守护进程**

****例 1:** 程序解释 isDaemon()和守护进程方法。**

**这是一个简单的例子来解释我们如何检查下面线程的性质或状态，在这个例子中，我们通过使用 **isDaemon()** 和**守护进程**方法来检查主线程的性质。这里我们使用 current_thread()方法，该方法简化了当前正在执行的线程，我们将其与 **isDaemon()** 和**守护程序**方法一起使用，以检查当前线程的性质或状态。这段代码的输出是 False 和 False，因为 current_thread 是主线程，并且总是一个非守护线程。**

## **蟒蛇 3**

```
# import module
from threading import *

print(current_thread().isDaemon())

print(current_thread().daemon)
```

****输出:****

```
False
False
```

****例 2:****

**在这个例子中，我们已经创建了一个函数来检查线程是否是守护进程，然后我们创建了一个新的线程 **thread_1** ，它当前是非守护进程线程和非活动线程，然后我们检查线程的状态或性质，输出变为 False 在此之后我们启动一个线程，现在线程再次成为活动线程，我们检查它的状态，再次输出为 False 这意味着不是主线程是非守护进程，但是其他创建的线程也是非守护进程。**

## **蟒蛇 3**

```
# import module
from threading import *

def fun_daemon():
  print("GFG")

thread_1 = Thread(target=fun_daemon)
print(thread_1.isDaemon())
thread_1.start()
print(thread_1.daemon)
```

****输出:****

```
False
GFG
False
```

## **将非守护程序更改为守护程序**

**正如我们之前看到的，如何检查以下线程是守护进程还是非守护进程，这里我们了解如何将以下非守护进程线程更改为守护进程。**

**A **setDaemon()** 是用于将给定线程的非守护进程性质更改为守护进程性质的方法。 **setDaemon()** 方法只接受一个布尔值参数( ***【真】*** 或 ***【假】*** )。**

> ****语法:** Thread_name.setDaemon()**
> 
> **#这里 Thread_name 指的是你用过的线程的名称。**
> 
> ****参数:** ( ***真**或**假*****
> 
>  ***   如果为真，则将此线程标记为守护线程
> *   如果为 False，则将此线程标记为非守护线程。**

****示例:****

## **蟒蛇 3**

```
# import module
from threading import *

def fun():
    print("Geeks For Geeks")

T = Thread(target = fun)

print("GFG")
print(T.isDaemon())

# set thread as Daemon
T.setDaemon(True) 

# check status
print(T.isDaemon())
T.start()
```

****输出:****

```
GFG
False
True
Geeks For Geeks
```

****说明:****

**在上面的例子中，首先我们导入一个库**线程**然后我们定义一个新的函数 **fun()** 在下一点我们创建一个新的线程变量 **T.** 目前， **T** 是一个非活动线程我们还没有执行 **start()** 方法， 这里我们将检查线程 **T** 的状态，输出为 **False** 接下来我们使用方法 **setDaemon()** 来改变线程的性质 **T** 再次使用该方法后我们将检查后续线程的状态此时输出为 **True** 。 **T21】****

## ****将主线程改为守护线程****

**如果我们想要将本质上总是非守护进程的主线程改变为守护进程，那么我们将得到一个 ***RuntimeError*** ，因为当程序启动时，主线程也会启动，所以主线程是一个活动线程，而活动线程没有被设置为守护进程。**

****示例:****

## **蟒蛇 3**

```
# import module
from threading import *

print(current_thread().setDaemon(True))
```

****输出:****

```
RuntimeError: cannot set daemon status of active thread
```