# Python–记录元组中的计数元素

> 原文:[https://www . geesforgeks . org/python-count-elements-in-record-tuple/](https://www.geeksforgeeks.org/python-count-elements-in-record-tuple/)

有时，在处理记录形式的数据时，我们可能会遇到一个问题，即我们需要找到收到的所有记录的元素总数。这是数据科学领域中非常常见的应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`len()` +生成器表达式**
这是实现解决这个任务最基本的方法。在这种情况下，我们使用生成器表达式迭代整个嵌套列表，并使用`len()`获得元素的计数。

```
# Python3 code to demonstrate working of
# Record elements count
# using len() + generator expression

# initialize list 
test_list = [(2, 4), (6, 7), (5, 1), (6, 10), (8, 7)]

# printing original list 
print("The original list : " + str(test_list))

# Record elements count
# using len() + generator expression
res = len(list((int(j) for i in test_list for j in i)))

# printing result
print("The total count of list is : " + str(res))
```

**Output :**

```
The original list : [(2, 4), (6, 7), (5, 1), (6, 10), (8, 7)]
The total count of list is : 10

```