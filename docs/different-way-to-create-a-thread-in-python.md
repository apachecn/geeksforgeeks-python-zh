# 在 Python 中创建线程的不同方式

> 原文:[https://www . geesforgeks . org/不同方式创建 python 线程/](https://www.geeksforgeeks.org/different-way-to-create-a-thread-in-python/)

一个 **线程** 是一个可以被调度执行的进程内的实体。此外，它是操作系统中可以执行的最小处理单元。

## 创建线程有多种方式:

**1)不使用显式函数创建线程:**

通过导入模块并分别创建*线程*类对象，我们可以轻松创建一个 t *hread* 。这是一种创建*螺纹*的面向功能的方式。

## 蟒蛇 3

```
# Import required modules
from threading import *    

# Explicit function
def display() :                
  for i in range(10) :
    print("Child Thread")

# Driver Code    

# Create object of thread class    
Thread_obj = Thread(target=display)        

# Executing child thread
Thread_obj.start()            

# Executing main thread
for i in range(10):            
  print('Main Thread')
```

```
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread  

```

在上面的例子中，我们创建了一个显式函数 *display()* ，它打印*子线程* 10 次。然后我们使用*线程*模块创建了一个名为 *Thread_obj* 的 *Thread* 类对象。第一个*线程*针对*显示()*方法即*显示()*方法将由这个*线程*对象执行，主*线程*(第二个)针对*进行*循环，将由主*线程*负责执行 10 次*。*

**注意:**这里哪个线程先获得机会(*主线程*或*子线程*)取决于 Python 虚拟机(PVM)中存在的线程调度器，所以我们无法预测输出。

**2)通过扩展线程类创建线程:**

在这个方法中，我们将从*穿线*模块扩展*穿线*类。这种创建线程的方法也被称为面向对象方法。

## 蟒 3

```
# Import required module
from threading import *

# Extending Thread class
class Mythread(Thread):

    # Target function for thread
    def run(self):
        for i in range(10):
            print('Child Thread')

# Driver Code

# Creating thread class object
t = Mythread()

# Execution of target function
t.start()

# Executed by main thread
for i in range(10):
    print('Main Thread')
```

```
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread

```

在上面的例子中，我们创建了一个扩展*线程*类的类，在这个类中，我们必须覆盖*run()*方法，该方法将是我们的*子线程*的目标函数，当 *start()* 方法被调用时，它将启动*线程*的 *run()* 方法(目标函数)的执行。

**3。创建线程而不扩展线程类:**

创建*线程*的另一种面向对象方式是不扩展任何线程类来创建线程。

## 蟒 3

```
# Import required modules
from threading import *

# Creating class
class Gfg:

    # Creating instance method
    def method1(self):
        for i in range(10):
            print('Child Thread')

# Driver Code

# Creating object of Gfg class
obj = Gfg()

# Creating object of thread by
# targeting instance method of Gfg class
thread_obj = Thread(target=obj.method1)

# Call the target function of threa
thread_obj.start()

# for loop executed by main thread
for i in range(10):
    print('Main Thread')
```

```
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Child Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread
Main Thread

```

在上面的程序中，我们分别创建了 thread 类的对象和 *Gfg* 类的对象，而每当我们创建 *thread* 类的对象时，那一次我们也必须提到目标函数。线程类对象的目标是 *Gfg 类*的实例方法。要开始执行目标函数，我们必须调用 *start()* 方法。