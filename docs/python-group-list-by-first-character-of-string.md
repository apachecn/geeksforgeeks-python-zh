# Python–按字符串第一个字符分组列表

> 原文:[https://www . geesforgeks . org/python-group-list-by-first-character-of-string/](https://www.geeksforgeeks.org/python-group-list-by-first-character-of-string/)

有时，我们有一个用例，在这个用例中，我们需要通过各种因素对字符串进行分组，比如第一个字母或任何其他因素。这些类型的问题是数据库查询的典型问题，因此可能会在编程时出现在 web 开发中。本文重点介绍了一种通过字符串首字母进行分组的方法。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`next() + lambda` +循环**
以上 3 个函数的组合就是用朴素的方法来解决这个特殊的问题。lambda 函数执行查找类似初始字符的任务，next 函数有助于向前迭代。

```py
# Python3 code to demonstrate
# Initial Character Case Categorization
# using next() + lambda + loop

# initializing list
test_list = ['an', 'a', 'geek', 'for', 'g', 'free']

# printing original list
print("The original list : " + str(test_list))

# using next() + lambda + loop
# Initial Character Case Categorization
util_func = lambda x, y: x[0] == y[0]
res = []
for sub in test_list:
    ele = next((x for x in res if util_func(sub, x[0])), [])
    if ele == []:
        res.append(ele)
    ele.append(sub)

# print result
print("The list after Categorization : " + str(res))
```

**Output :**

```py
The original list : ['an', 'a', 'geek', 'for', 'g', 'free']
The list after Categorization : [['an', 'a'], ['geek', 'g'], ['for', 'free']]

```