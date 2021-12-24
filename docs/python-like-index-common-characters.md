# 类似 Python 的索引常用字符

> 原文:[https://www . geesforgeks . org/python-like-index-common-characters/](https://www.geeksforgeeks.org/python-like-index-common-characters/)

有时我们会遇到这种类型的问题，我们需要将一个列表中的每个元素与另一个相交。这类问题通常发生在我们拥有综合信息的开发中，比如不同列表中的姓名。让我们讨论执行这项任务的某些方法。

**方法一:使用列表理解+ `zip() + intersection()`**
列表理解完成相似指标元素的相交任务。zip 函数的任务是将结果字符串连接成单个列表和返回列表。

```py
# Python3 code to demonstrate 
# Like Index Common characters
# using list comprehension + zip() + intersection()

# initializing lists 
test_list1 = ["Geeksfor", "is", "be"]
test_list2 = ['Geeks', 'sb', 'ste']

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using list comprehension + zip()
# Like Index Common characters + intersection()
res = ["".join(list(set(i).intersection(set(j)))) for i, j in zip(test_list1, test_list2)]

# printing result 
print ("The list after element intersection is : " + str(res))
```

**Output :**

```py
The original list 1 is : ['Geeksfor', 'is', 'be']
The original list 2 is : ['Geeks', 'sb', 'ste']
The list after element intersection is : ['sGek', 's', 'e']

```