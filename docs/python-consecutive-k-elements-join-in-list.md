# Python–列表中连续的 K 个元素连接

> 原文:[https://www . geesforgeks . org/python-continuous-k-elements-join-in-list/](https://www.geeksforgeeks.org/python-consecutive-k-elements-join-in-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要将每 K 个字符连接到一个集合中。这种类型的应用程序可以在许多领域有用例，比如日常和竞争性编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
这是执行这个任务的方法之一。在这种情况下，我们使用列表切片遍历列表并连接元素，然后返回聚合列表。

```
# Python3 code to demonstrate 
# Consecutive K elements join in List
# using List comprehension

# Initializing list
test_list = ['g', 'f', 'g', 'i', 's', 'b', 'e', 's', 't']

# printing original list
print("The original list is : " + str(test_list))

# Initializing K 
K = 3

# Consecutive K elements join in List
# using List comprehension
res = [ "".join(test_list[idx : idx + K]) for idx in range(len(test_list) - K + 1) ]

# printing result 
print ("List after consecutive joining : " + str(res))
```

**Output :**

> 原列表为:['g '，' f '，' g '，' I '，' s '，' b '，' e '，' s '，' t']
> 连续加入后的列表:['gfg '，' fgi '，' gis '，' isb '，' sbe '，' bes '，' est']