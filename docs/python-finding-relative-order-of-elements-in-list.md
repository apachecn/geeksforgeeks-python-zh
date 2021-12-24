# Python |查找列表中元素的相对顺序

> 原文:[https://www . geesforgeks . org/python-find-相对-列表中元素的顺序/](https://www.geeksforgeeks.org/python-finding-relative-order-of-elements-in-list/)

有时我们有一个未排序的列表，我们希望找到元素被排序时的实际位置，也就是说，我们希望构建一个列表，如果列表被排序，它可以给出每个元素的位置。这在 web 开发和竞争性编程领域有很好的应用。让我们讨论一下实现这一点的某些方法。

**方法一:使用`sorted() + index()` +列表理解**
以上所有功能可以组合起来完成这个特定的任务。排序函数返回排序顺序，索引由索引函数完成。列表理解的任务是对整个列表元素进行操作，并整合这两项任务。

```py
# Python3 code to demonstrate
# Finding relative order of elements in list
# using sorted() + index() + list comprehension

# initializing list
test_list = [6, 3, 1, 2, 5, 4]

# printing original list
print("The original list is : " + str(test_list))

# using sorted() + index() + list comprehension
# Finding relative order of elements in list
temp = sorted(test_list)    
res = [temp.index(i) for i in test_list]

# printing result
print ("The relative ordering list is : " + str(res))
```

**Output :**

```py
The original list is : [6, 3, 1, 2, 5, 4]
The relative ordering list is : [5, 2, 0, 1, 4, 3]

```