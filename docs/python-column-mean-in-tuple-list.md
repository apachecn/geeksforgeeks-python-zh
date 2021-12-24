# Python |元组列表中的列均值

> 原文:[https://www . geesforgeks . org/python-column-mean in-tuple-list/](https://www.geeksforgeeks.org/python-column-mean-in-tuple-list/)

有时，在处理记录时，我们会遇到一个问题，即我们需要对元组列表容器中的所有列进行平均。这种应用在 web 开发领域很常见。让我们讨论执行这项任务的某些方法。

**方法#1:使用 sum() +列表理解+ zip()**
该任务可以使用上述功能的组合来执行。在本文中，我们使用 zip()累积相似的索引元素，即列，然后使用列表理解迭代它们，并使用 sum()执行求和。我们将每个结果除以行数进行平均计算。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Column Mean in tuple list
# using list comprehension + sum() + zip()

# initialize list
test_list = [(1, 2, 3), (6, 7, 6), (1, 6, 8)]

# printing original list
print("The original list : " + str(test_list))

# Column Mean in tuple list
# using list comprehension + sum() + zip()
res = [sum(ele) / len(test_list) for ele in zip(*test_list)]

# printing result
print("The Cummulative column mean is : " + str(res))
```

**Output : **

```py
The original list : [(1, 2, 3), (6, 7, 6), (1, 6, 8)]
The Cummulative column mean is : [2.6666666666666665, 5.0, 5.666666666666667]
```

**方法 2:使用 zip() + map() + sum()**
此方法与上述方法类似。在这种情况下，由列表理解执行的任务由 map()执行，它将列的求和扩展到压缩的元素。我们将每个结果除以行数进行平均计算。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Column Mean in tuple list
# using zip() + map() + sum()

def avg(list):
    return sum(list)/len(list)

# initialize list
test_list = [(1, 2, 3), (6, 7, 6), (1, 6, 8)]

# printing original list
print("The original list : " + str(test_list))

# Column Mean in tuple list
# using zip() + map() + sum()
res = list(map(avg, zip(*test_list)))

# printing result
print("The Cummulative column mean is : " + str(res))
```

**Output : **

```py
The original list : [(1, 2, 3), (6, 7, 6), (1, 6, 8)]
The Cummulative column mean is : [2.6666666666666665, 5.0, 5.666666666666667]
```