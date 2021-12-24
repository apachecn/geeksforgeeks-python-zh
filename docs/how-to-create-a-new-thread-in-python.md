# 如何在 Python 中创建新线程

> 原文:[https://www . geesforgeks . org/如何在 python 中创建新线程/](https://www.geeksforgeeks.org/how-to-create-a-new-thread-in-python/)

python 中的[](https://www.geeksforgeeks.org/thread-in-operating-system/)**线程是进程中的一个实体，可以被调度执行。简单地说，线程是由计算机执行的计算过程。它是程序中的一系列指令，可以独立于其他代码执行。**

**在 Python 中，有两种方法可以创建新的线程。在本文中，我们还将利用 Python 中的 [**线程模块**](https://www.geeksforgeeks.org/thread-based-parallelism-python/) 。下面是这些过程的详细列表:**

### ****1。使用类**创建 python 线程**

**下面是一个编码示例，后面是使用 python 中的类创建新线程的代码解释。**

## **蟒蛇 3**

```py
# import the threading module
import threading

class thread(threading.Thread):
    def __init__(self, thread_name, thread_ID):
        threading.Thread.__init__(self)
        self.thread_name = thread_name
        self.thread_ID = thread_ID

        # helper function to execute the threads
    def run(self):
        print(str(self.thread_name) +" "+ str(self.thread_ID));

thread1 = thread("GFG", 1000)
thread2 = thread("GeeksforGeeks", 2000);

thread1.start()
thread2.start()

print("Exit")
```

****输出:****

```py
GFG 1000
GeeksforGeeks 2000
Exit
```

**现在让我们看看我们在代码中做了什么。**

1.  **我们创建了线程类的子类。**
2.  **然后我们覆盖线程类的 __init__ 函数。**
3.  **然后我们重写 run 方法来定义线程的行为。**
4.  **start()方法启动一个 Python 线程。**

### ****2。使用函数**创建 python 线程**

**下面的代码显示了使用函数创建新线程:**

## **蟒蛇 3**

```py
from threading import Thread
from time import sleep

# function to create threads
def threaded_function(arg):
    for i in range(arg):
        print("running")

        # wait 1 sec in between each thread
        sleep(1)

if __name__ == "__main__":
    thread = Thread(target = threaded_function, args = (10, ))
    thread.start()
    thread.join()
    print("thread finished...exiting")
```

****输出:****

```py
running
running
running
running
running
running
running
running
running
running
thread finished...exiting
```

**所以我们在上面的代码中所做的，**

1.  **我们定义了一个函数来创建一个线程。**
2.  **然后，我们使用线程模块创建一个线程，调用函数作为它的目标。**
3.  **然后我们使用 start()方法启动 Python 线程。**