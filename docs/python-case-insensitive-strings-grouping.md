# Python–不区分大小写的字符串分组

> 原文:[https://www . geesforgeks . org/python-不区分大小写-字符串-分组/](https://www.geeksforgeeks.org/python-case-insensitive-strings-grouping/)

有时，我们有一个用例，在这个用例中，我们需要通过各种因素对字符串进行分组，比如第一个字母或任何其他因素。这些类型的问题是数据库查询的典型问题，因此可能会在编程时出现在 web 开发中。本文重点介绍一种不区分大小写的分组方法，即将所有相同但大小写不同的字符串分组。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`next()` + lambda + loop**
以上 3 个函数的组合就是用朴素的方法来解决这个特殊的问题。lambda 函数执行查找相似案例的任务，next 函数有助于向前迭代。

```py
# Python3 code to demonstrate
# Case Insensitive Strings Grouping
# using next() + lambda + loop

# initializing list
test_list = ['man', 'a', 'gEek', 'for', 'GEEK', 'FoR']

# printing original list
print("The original list : " + str(test_list))

# using next() + lambda + loop
# Case Insensitive Strings Grouping
util_func = lambda x, y: str.lower(x) == str.lower(y)
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
The original list : ['man', 'a', 'gEek', 'for', 'GEEK', 'FoR']
The list after Categorization : [['man'], ['a'], ['gEek', 'GEEK'], ['for', 'FoR']]

```