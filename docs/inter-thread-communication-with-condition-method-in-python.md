# Python 中带条件()方法的线程间通信

> 原文:[https://www . geesforgeks . org/线程间通信-python 中的条件方法/](https://www.geeksforgeeks.org/inter-thread-communication-with-condition-method-in-python/)

本文基于我们如何使用 Condition()方法实现**线程间通信，**让我们在下面讨论这个主题:

先简单讨论一下**线程间通信**，然后再讨论一下**线程间通信的条件()**实现，当任何一个线程需要另一个线程的东西时，它们会组织它们之间的通信，有了这个通信，它们就会满足自己的需求。这意味着对于任何类型的需求，它都是线程间通信的过程。

### 条件法

我们可以说，使用**条件()**方法实现线程间通信是对用于线程间通信的事件对象的升级。这里的条件表示线程之间某种类型的状态变化，如“发送通知”、“收到通知”。请参见下面条件对象是如何创建的

**语法:**

```
condition_object = threading.condition( )
```

在这种情况下，线程可以等待该条件，一旦该条件执行，线程就可以根据该条件进行修改。简单地说，我们可以说条件对象允许线程等待，直到另一个线程通知它们。条件对象始终与**锁(RLock)** 概念内部关联。

下面我们讨论条件类的一些方法:

1.  release
2.  obtain
3.  notification
4.  wait for
5.  All notifications ()

*   **release()方法:**当线程满足条件对象的需求时，我们将使用 **release()** 方法，该方法帮助我们将条件对象从其任务中释放出来，并突然释放线程获得的内部锁。

```
Syntax: condition_object.release()
```

*   **acquire()方法:**当我们想要获取或接管任何线程间通信的条件对象时，我们总是使用 **acquire()** 方法。当我们想要使用条件类实现线程间通信时，acquire()方法是必需的。当我们使用这个方法时，线程会突然获得系统的内部锁。

```
Syntax: condition_object.acquire()
```

*   **notify()方法:**当我们想只向一个处于等待状态的线程发送通知时，我们总是使用 **notify()** 方法。这里，如果一个线程想要成为条件对象的升级，那么使用 notify()。

```
Syntax :condition_object.notify()                                      
```

*   **等待(时间)方法:****等待()**方法可用于让线程等待，直到收到通知，也直到给定时间结束。简单来说我们可以说线程是要等到**通知()**方法的执行没有完成。我们可以在其中使用时间，如果我们设置了一个特定的时间，那么执行将停止，直到时间结束，之后它将执行仍然剩余的指令。

```
Syntax: condition_object.wait()
Parameter:Time 
```

*   **notifyAll()方法:**这里 **notifyAll()** 方法用于发送所有等待线程的通知。如果所有线程都在等待条件对象更新，则**通知所有线程()**将使用。

```
Syntax: condition_object.notifyAll()
```

现在让我们举一个简单的例子来说明如何使用**获取**和**发布**方法，以及它们如何在整个程序中工作:

**例 1:**

## 蟒 3

```
# code
# import modules

import threading 
import time

obj1= threading.Condition()

def task ():
  obj1.acquire()
  print('addition of 1 to 10 ')
  add= 0
  for i in range ( 1 , 11 ):
    add = add+i
  print(add)
  obj1.release()
  print('the condition object is releases now')

t1 = threading.Thread(target = task)
t1.start()
```

**输出**

```
addition of 1 to 10 
55
the condition object is releases now
```

在上面的例子中，我们使用了**获取()**和**释放()**的方法，可以用来获取或获取条件对象，并在任务完成后释放条件对象。首先，我们导入所需的模块，然后我们创建条件对象，即 **obj1** ，然后我们创建并启动线程 **t1** ，在我们使用 **acquire()** 方法的任务命名函数中，我们从这些获取条件对象，并从这里启动线程的内部锁定。在最后完成指令后，我们释放条件对象，线程的内部锁也被释放。

**例 2:**

在这个例子中，我们使用了其他方法来解释它们如何在整个程序中工作:-

## python 3

```
# code

# import modules

import time
from threading import *
import random

class appointment:

  def patient(self):
    condition_object.acquire()
    print('patient john waiting for appointment')
    condition_object.wait()   # Thread is in waiting state
    print('successfully got the appointment')
    condition_object.release()

  def doctor(self):
    condition_object.acquire()
    print('doctor jarry checking the time for appointment')
    time=0 
    time=random.randint(1,13)
    print('time checked')
    print('oppointed time is {} PM'.format(time))
    condition_object.notify()
    condition_object.release()

condition_object = Condition()
class_obj=appointment()

T1 = Thread(target=class_obj.patient)

T2 = Thread(target=class_obj.doctor)

T1.start()

T2.start()
```

**Output**

```
patient john waiting for appointment
doctor jarry checking the time for appointment
time checked
oppointed time is 4 PM
successfully got the appointment
```

这是一个简单的例子来解释 **Condition()** 类及其方法在线程中的使用。此外，这里我们使用了一个病人和医生的例子，病人和医生如何首先获取条件，然后如何通知他们，最后两者也释放条件对象。让我们首先创建一个类预约，它有两个功能，分别命名为**患者()**和**医生()**，然后我们创建了两个线程 **T1** 和 **T2** 。在 **acquire()** 方法的帮助下，**医生**和**患者**都在他们的第一个语句中获取了条件对象，由此两个线程都被内部锁定。现在**患者**必须等待预约，在**等待()**方法执行后得到预约，医生开始检查他选择的时间是否可以预约，当医生选择了时间时，它将通过**通知()**方法通知处于等待状态的线程。接下来在**通知()**方法之后，患者得到了他们的通知和产品两者。然后经过这一切，两个线程通过 **release()** 方法释放条件对象，内部锁释放。