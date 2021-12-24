# Python |列表中出现频率最大的元素

> 原文:[https://www . geesforgeks . org/python-列表中出现频率最大的元素/](https://www.geeksforgeeks.org/python-element-with-largest-frequency-in-list/)

这是程序员经常遇到的最基本的操作之一。无论是开发还是竞争性编程，掌握这个实用程序都是非常必要的，因为它有助于执行许多涉及到这个任务的子任务。让我们讨论实现这一操作的各种方法。

**方法#1:天真法**
作为蛮力法，我们只需要对所有元素进行计数，然后只需要返回元素整体计数保持最大值就结束了。面对这个问题，这是人们可以想到执行的基本方法。

```
# Python3 code to demonstrate 
# to get most frequent element
# using naive method

# initializing list
test_list = [9, 4, 5, 4, 4, 5, 9, 5, 4]

# printing original list
print ("Original list : " + str(test_list))

# using naive method to 
# get most frequent element
max = 0
res = test_list[0]
for i in test_list:
    freq = test_list.count(i)
    if freq > max:
        max = freq
        res = i

# printing result
print ("Most frequent number is : " + str(res))
```

**输出:**

```
Original list : [9, 4, 5, 4, 4, 5, 9, 5, 4]
Most frequent number is : 4

```

**方法 2:使用`max() + set()`**
转换列表来设置和最大化列表中每个数字的计数功能，这个任务可以轻松实现，也是实现这个任务最优雅的方式。

```
# Python3 code to demonstrate 
# to get most frequent element
# using max() + set()

# initializing list
test_list = [9, 4, 5, 4, 4, 5, 9, 5, 4]

# printing original list
print ("Original list : " + str(test_list))

# using max() + set() to 
# get most frequent element
res = max(set(test_list), key = test_list.count)

# printing result
print ("Most frequent number is : " + str(res))
```

**输出:**

```
Original list : [9, 4, 5, 4, 4, 5, 9, 5, 4]
Most frequent number is : 4

```

**方法#3:使用`statistics.mode()`**
模式表示数学中的最大频率元素，python 将整个库专用于统计函数，这也可以用来实现这个任务。

```
# Python3 code to demonstrate 
# to get most frequent element
# using statistics.mode()
import statistics

# initializing list
test_list = [9, 4, 5, 4, 4, 5, 9, 5, 4]

# printing original list
print ("Original list : " + str(test_list))

# using statistics.mode() to 
# get most frequent element
res = statistics.mode(test_list)

# printing result
print ("Most frequent number is : " + str(res))
```

**输出:**

```
Original list : [9, 4, 5, 4, 4, 5, 9, 5, 4]
Most frequent number is : 4

```

**方法#4:使用`collections.Counter.most_common()`**
不太为人所知的方法来完成这个特定的任务，`Counter()`使用最常用的函数来一行完成这个任务。这是实现这一点的创新和不同的方式。

```
# Python3 code to demonstrate 
# to get most frequent element
# using collections.Counter.most_common()
from collections import Counter

# initializing list
test_list = [9, 4, 5, 4, 4, 5, 9, 5, 4]

# printing original list
print ("Original list : " + str(test_list))

# using most_common to 
# get most frequent element
test_list = Counter(test_list)
res = test_list.most_common(1)[0][0]

# printing result
print ("Most frequent number is : " + str(res))
```

**输出:**

```
Original list : [9, 4, 5, 4, 4, 5, 9, 5, 4]
Most frequent number is : 4

```