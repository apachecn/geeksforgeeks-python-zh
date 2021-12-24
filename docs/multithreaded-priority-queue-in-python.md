# Python 中的多线程优先级队列

> 原文:[https://www . geesforgeks . org/多线程-优先级-python 中的队列/](https://www.geeksforgeeks.org/multithreaded-priority-queue-in-python/)

队列模块主要用于管理在多个线程上处理大量数据。它支持创建一个新的队列对象，该对象可以包含不同数量的项目。
使用`get()` 和`put()`方法分别添加或删除队列中的项目。下面是用于管理队列的操作列表:

*   **get():** 用于向队列中添加一个项目。
*   **put():** 用于从队列中移除一个项目。
*   **qsize():** 用于查找队列中的项目数。
*   **empty():** 它根据队列是否为空返回一个布尔值。
*   **full():** 它根据队列是否已满返回一个布尔值。

一个[优先级队列](https://www.geeksforgeeks.org/priority-queue-in-python/)是队列的扩展，具有以下属性:

*   优先级高的元素在优先级低的元素之前出队。
*   如果两个元素具有相同的优先级，则根据它们在队列中的顺序提供服务。

下面是一个代码示例，解释了创建多线程优先级队列的过程:

**示例:**

```
import queue
import threading
import time

thread_exit_Flag = 0

class sample_Thread (threading.Thread):
   def __init__(self, threadID, name, q):
      threading.Thread.__init__(self)
      self.threadID = threadID
      self.name = name
      self.q = q
   def run(self):
      print ("initializing " + self.name)
      process_data(self.name, self.q)
      print ("Exiting " + self.name)

# helper function to process data        
def process_data(threadName, q):
   while not thread_exit_Flag:
      queueLock.acquire()
      if not workQueue.empty():
         data = q.get()
         queueLock.release()
         print ("% s processing % s" % (threadName, data))
      else:
         queueLock.release()
         time.sleep(1)

thread_list = ["Thread-1", "Thread-2", "Thread-3"]
name_list = ["A", "B", "C", "D", "E"]
queueLock = threading.Lock()
workQueue = queue.Queue(10)
threads = []
threadID = 1

# Create new threads
for thread_name in thread_list:
   thread = sample_Thread(threadID, thread_name, workQueue)
   thread.start()
   threads.append(thread)
   threadID += 1

# Fill the queue
queueLock.acquire()
for items in name_list:
   workQueue.put(items)

queueLock.release()

# Wait for the queue to empty
while not workQueue.empty():
   pass

# Notify threads it's time to exit
thread_exit_Flag = 1

# Wait for all threads to complete
for t in threads:
   t.join()
print ("Exit Main Thread")
```

 **输出:**

```
initializing Thread-1
initializing Thread-2initializing Thread-3

Thread-2 processing AThread-3 processing B

Thread-3 processing C
Thread-3 processing D
Thread-2 processing E
Exiting Thread-2
Exiting Thread-1
Exiting Thread-3
Exit Main Thread
```

**注意:**输出可能因设备规格和处理能力而异。