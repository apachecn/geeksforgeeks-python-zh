# Python |通过元组中元素的计数扩展元组

> 原文:[https://www . geesforgeks . org/python-按元组中元素的计数扩展元组/](https://www.geeksforgeeks.org/python-extend-tuples-by-count-of-elements-in-tuple/)

有时，在处理数据时，我们可以有一个应用程序，其中我们需要根据元素计数的数量来复制元组元素。这是非常独特的应用，但在某些情况下可能会出现。让我们讨论执行这项任务的某些方法。

**方法#1:使用嵌套循环**
这是可以执行该任务的蛮力方法。在这种情况下，外部循环用于对列表中的每个元素进行迭代，内部循环用于通过外部循环添加与相应元组的长度相等的相似元素。

```
# Python3 code to demonstrate working of
# Extend tuples by count in list
# using nested loop

# initialize list of tuple
test_list = [('1', '4', '6'), ('5', '8'), ('2', '9'), ('1', )]

# printing original tuples list
print("The original list : " + str(test_list))

# Extend tuples by count in list
# using nested loop
res = []
for sub in range(len(test_list)):
    for ele in range(len(test_list[sub])):
        res.append(test_list[sub])

# printing result
print("The modified and extended list is : " + str(res))
```

**Output :**

> 原始列表:[('1 '，' 4 '，' 6 ')，(' 5 '，' 8 ')，(' 2 '，' 9 '，(' 1 '，)]
> 修改扩展后的列表为:[('1 '，' 4 '，' 6 ')，(' 1 '，' 4 '，' 6 ')，(' 5 '，' 8 '，(' 5 '，' 8 ')，(' 2 '，' 9 ')，(' 2 '，' 9 ')，(' 1 '，)