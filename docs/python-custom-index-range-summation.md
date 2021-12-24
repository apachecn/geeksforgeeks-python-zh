# Python |自定义索引范围求和

> 原文:[https://www . geesforgeks . org/python-custom-index-range-summary/](https://www.geeksforgeeks.org/python-custom-index-range-summation/)

开发和有时机器学习应用程序需要以定制的方式将列表拆分成更小的列表，即在某些值上进行拆分，然后求和。这是一个非常有用的工具。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `zip() + sum()`**
通过耦合列表理解和 zip()的力量，可以实现这个任务。在这种情况下，我们压缩列表的开头和结尾，然后在列表到达时继续切片，并从中剪切出新的列表。使用 sum()执行求求和的任务。

```py
# Python3 code to demonstrate 
# Custom Index Range Summation
# using list comprehension + zip() + sum()

# initializing string 
test_list = [1, 4, 5, 6, 7, 3, 5, 9, 2, 4]

# initializing split index list 
split_list = [2, 5, 7]

# printing original list
print ("The original list is : " + str(test_list))

# printing original split index list
print ("The original split index list : " + str(split_list))

# using list comprehension + zip() + sum()
# Custom Index Range Summation
res = [sum(test_list[i : j]) for i, j in zip([0] + 
                 split_list, split_list + [None])]

# printing result
print ("The splitted lists summation are : " + str(res))
```

**Output :**

```py
The original list is : [1, 4, 5, 6, 7, 3, 5, 9, 2, 4]
The original split index list : [2, 5, 7]
The splitted lists summation are : [5, 18, 8, 15]

```