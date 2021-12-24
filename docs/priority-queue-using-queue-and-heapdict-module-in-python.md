# 使用 Python 中的队列和 Heapdict 模块的优先级队列

> 原文:[https://www . geesforgeks . org/priority-queue-use-queue-and-heapdict-module-in-python/](https://www.geeksforgeeks.org/priority-queue-using-queue-and-heapdict-module-in-python/)

优先级队列是队列的扩展，具有以下属性。

*   优先级高的元素在优先级低的元素之前出队。
*   如果两个元素具有相同的优先级，则根据它们在队列中的顺序提供服务。

## 尾巴！尾巴！优先级队列(maxsize)

它是优先级队列的构造函数。maxsize 是可以插入队列的元素数，默认值为 0。如果 maxsize 值小于或等于 0，则队列大小为无穷大。项目按优先级顺序检索(最低优先)。
**功能-**

*   **put()–**将项目放入队列。
*   **get()–**从队列中移除并返回一个项目。
*   **qsize()–**返回当前队列大小。
*   **空()–**如果队列为空，则返回真，否则返回假。它相当于 qsize()==0。
*   **已满()–**如果队列已满，则返回真，否则返回假。相当于 qsize() > =maxsize。

**注意:**`empty()``full()``qsize()`不可靠，因为它们冒着队列大小可能改变的比赛条件的风险。

**示例:**

```py
from queue import PriorityQueue

q = PriorityQueue()

# insert into queue
q.put((2, 'g'))
q.put((3, 'e'))
q.put((4, 'k'))
q.put((5, 's'))
q.put((1, 'e'))

# remove and return 
# lowest priority item
print(q.get())
print(q.get())

# check queue size
print('Items in queue :', q.qsize())

# check if queue is empty
print('Is queue empty :', q.empty())

# check if queue is full
print('Is queue full :', q.full())
```

**输出:**

```py
(1, 'e')
(2, 'g')
Items in queue : 3
Is queue empty : False
Is queue full : False

```

## heapdict()

Heapdict 实现了可变映射 ABC，这意味着它的工作方式非常像普通的 Python 字典。它被设计用作优先队列。除了普通`dict()`提供的功能外，它还有`popitem()`和`peekitem()`功能，返回优先级最低的那对。与 heapq 模块不同，HeapDict 支持有效地更改现有对象的优先级(“递减键”)。改变优先级对于很多算法都很重要，比如迪克斯特拉算法和 A*。

**功能-**

*   **清除(自我)**–清除()- >无。从 d 中移除所有项目。
*   **peek item(self)**–d . peek item()->(k，v)，返回值最低的(key，value)对；但是如果 D 为空，则引发键错误。
*   **pop item(self)**–d . pop item()->(k，v)，移除并返回最低值的(key，value)对；但是如果 D 为空，则引发键错误。
*   **get(self，key，default = None**)–D . get(k[，d]) - > D[k]如果 D 中有 k，则 d. d 默认为 None。
*   **物品(自身)**–D .物品()- >提供 D .物品视图的集合状物体
*   **键(自身)**–D . keys()->一个类似集合的对象，提供 D 的键的视图
*   **值(自我)**–D . values()->提供 D 值视图的对象

**示例:**

```py
import heapdict

h = heapdict.heapdict()

# Adding pairs into heapdict
h['g']= 2
h['e']= 1
h['k']= 3
h['s']= 4

print('list of key:value pairs in h:\n', 
      list(h.items()))
print('pair with lowest priority:\n',
      h.peekitem())
print('list of keys in h:\n',
      list(h.keys()))
print('list of values in h:\n',
      list(h.values()))
print('remove pair with lowest priority:\n',
      h.popitem())
print('get value for key 5 in h:\n',
      h.get(5, 'Not found'))

# clear heapdict h
h.clear()
print(list(h.items()))
```

**输出:**

```py
list of key:value pairs in h:
 [('g', 2), ('e', 1), ('k', 3), ('s', 4)]
pair with lowest priority:
 ('e', 1)
list of keys in h:
 ['g', 'e', 'k', 's']
list of values in h:
 [2, 1, 3, 4]
remove pair with lowest priority:
 ('e', 1)
get value for key 5 in h:
 Not found
[]

```