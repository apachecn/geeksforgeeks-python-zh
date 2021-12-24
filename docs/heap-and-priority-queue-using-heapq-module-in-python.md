# 使用 Python 中 heapq 模块的堆和优先级队列

> 原文:[https://www . geesforgeks . org/heap-and-priority-queue-use-heap q-module-in-python/](https://www.geeksforgeeks.org/heap-and-priority-queue-using-heapq-module-in-python/)

堆是广泛使用的树状数据结构，其中父节点满足下面给出的任何一个标准。

*   每个级别中父节点的值小于或等于其子节点的值–**min-heap。**
*   每个级别中父节点的值高于或等于其子节点的值–**max-heap。**

堆是完整的二叉树，用于实现优先级队列。最小堆在调度作业、调度电子邮件或根据优先级将资源分配给任务方面起着至关重要的作用。

### 优先队列

这些是抽象数据类型，是队列的一种特殊形式。队列中的元素具有分配给它们的优先级。根据优先级，优先级队列中的第一个元素将是优先级最高的元素。下面列出了与这些优先级队列相关的基本操作:

*   **为 _ 空:**检查队列是否为空。
*   **插入:**插入一个元素及其优先级。该元素将仅按照其优先级的顺序放置。
*   **弹出:**弹出优先级最高的元素。第一个元素将是具有最高优先级的元素。

优先级队列可以用于所有调度类型的进程。程序员可以决定是将最大的数字视为最高优先级，还是将最低的数字视为最高优先级。如果两个元素具有相同的优先级，那么它们将按照在队列中出现的顺序出现。

## Python 中的 heapq 模块

[Heapq](https://www.geeksforgeeks.org/heap-queue-or-heapq-in-python/) 模块是保留最小堆属性的堆队列算法(优先级队列算法)的实现。该模块获取一个项目列表并重新排列，使它们满足以下最小堆标准:

*   索引**‘I’**中的父节点小于或等于其子节点。
*   索引**‘I’**中节点的左子节点位于索引**‘(2 * I)+1’**中。
*   索引**‘I’**中节点的右子节点位于索引**‘(2 * I)+2’**中。

### 使用 heapq 模块的优先级队列

优先级队列在 Python 中实现为元组列表，其中元组包含优先级作为第一个元素，值作为下一个元素。

> 示例:[ (1，2)，(2，3)，(4，5)，(6，7)]
> 
> 考虑(1，2):
> 
> *   **优先级:1**
> *   **值/元素:2**

**示例:**

考虑一个简单的优先级队列实现，用于根据学生的卷号安排他们的演示。这里的卷号决定了学生出席的优先级。因为它是最小堆，所以卷号 1 被认为是最高优先级。

## 蟒蛇 3

```py
# import modules
import heapq as hq

# list of students
list_stu = [(5,'Rina'),(1,'Anish'),(3,'Moana'),(2,'cathy'),(4,'Lucy')]

# Arrange based on the roll number
hq.heapify(list_stu)

print("The order of presentation is :")

for i in list_stu:
  print(i[0],':',i[1])
```

**Output**

```py
The order of presentation is :
1 : Anish
2 : cathy
3 : Moana
5 : Rina
4 : Lucy

```

**例 2:**

现在让我们实现一个简单的调度程序，将作业分配给处理器。调度程序使用优先级队列来决定必须执行哪个任务。除了任务之外，还会有接近调度程序的中断。因此调度程序必须决定是执行中断还是现有任务。如果中断优先级较高，则首先执行，否则，一旦所有作业完成，中断将得到服务。为了实现这一点，使用 heapq 模块。方法如下。

*   要执行的任务被分配了优先级。优先级为“1”的元素被认为是最重要的任务。
*   所有任务都在一个优先级队列中，并使用 min-heap 属性进行维护。
*   任务得到服务，并且在进行中，只打印一条消息作为执行日志，说明哪个任务正在进行中。
*   中断及其优先级接近调度程序。
*   中断被推入优先级队列，保留最小堆属性。
*   具有最高优先级的任务/中断将首先被服务，并且它总是队列中的第一个元素。
*   一旦 task.interrupt 得到服务，它就会从堆队列中弹出。

## 蟒蛇 3

```py
import time
import heapq as hq

# jobs to be executed
jobs = [(2, 'task_1'), (5, 'task_2'), (1, 'task_4'),
        (4, 'task_5'), (3, 'task_3'), (1, 'task_8')]

# interrupts
interrupts = [(1, 'intr_1'), (2, 'intr_2'), (13, 'intr_3')]

i, j = 0, 0

# Arranging jobs in heap
hq.heapify(jobs)

print(jobs, "\n\n")

# scheduling the tasks
while len(jobs) != 0:

    # printing execution log
    print("The ", jobs[0][1], " with priority ",
          jobs[0][0], " in progress", end="")

    # servicing the tasks
    for _ in range(0, 5):

        print(".", end="")
        time.sleep(0.5)

    # pop the job that completed
    hq.heappop(jobs)

    # adding interrupts
    if j < len(interrupts):

        hq.heappush(jobs, interrupts[j])
        print("\n\nNew interrupt arrived!!", interrupts[j])
        print()
        j = j+1

    # job queue after arrival of interrupt
    print("\n Job queue currently :", jobs)
    print("\n")

print("\nAll interrupts and jobs completed!")
```

**输出**

<video class="wp-video-shortcode" id="video-491681-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200925132534/task_schduler_python.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200925132534/task_schduler_python.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200925132534/task_schduler_python.mp4)</video>