# Python |增加列表中的替代元素模式

> 原文:[https://www . geesforgeks . org/python-递增-替代-元素-列表中的模式/](https://www.geeksforgeeks.org/python-increasing-alternate-element-pattern-in-list/)

这篇特别的文章解决了一个非常具体的问题，即我们需要将每个替换元素作为重复元素的增加尺寸的模式来插入，以形成一个模式。这在示范项目中会有用处。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `enumerate()`**
在枚举函数的帮助下，列表理解可以用于执行这个特定的任务，其中我们使用元组，该元组使用枚举函数为插入增加每个替换元素的长度。

```py
# Python3 code to demonstrate
# increasing alternate element pattern
# using list comprehension + enumerate()

# initializing list 
test_list = [1, 2, 3, 4, 5]

# printing original list 
print("The original list : " + str(test_list))

# using list comprehension + enumerate()
# increasing alternate element pattern
res = [j for sub in ((i, '*' * k)
       for k, i in enumerate(test_list, 1))
       for j in sub]

# print result
print("The increasing element pattern list : " + str(res))
```

**Output :**

```py
The original list : [1, 2, 3, 4, 5]
The increasing element pattern list : [1, '*', 2, '**', 3, '***', 4, '****', 5, '*****']

```