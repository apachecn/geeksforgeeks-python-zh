# Python |频率等于 K 的元素

> 原文:[https://www . geesforgeks . org/python-elements-with-frequency-equal-k/](https://www.geeksforgeeks.org/python-elements-with-frequency-equal-k/)

这是程序员经常遇到的最基本的操作之一。无论是开发还是竞争性编程，掌握这个实用程序都是非常必要的，因为它有助于执行许多涉及到这个任务的子任务。让我们讨论实现这一操作的方法。

**方法#1:天真方法**
作为蛮力方法，我们只需要对所有元素进行计数，然后只返回计数等于 k 的元素，这是面对这个问题时可以想到执行的基本方法。

```py
# Python3 code to demonstrate 
# Elements with Frequency equal K
# using naive method

# initializing list
test_list = [9, 4, 5, 4, 4, 5, 9, 5]

# printing original list
print ("Original list : " + str(test_list))

# initializing K 
K = 3

# using naive method to 
# get most frequent element
res = []
for i in test_list:
    freq = test_list.count(i)
    if freq == K and i not in res:
        res.append(i)

# printing result
print ("Elements with count K are : " + str(res))
```

**Output :**

```py
Original list : [9, 4, 5, 4, 4, 5, 9, 5]
Elements with count K are : [4, 5]

```