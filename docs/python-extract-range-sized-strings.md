# Python–提取范围大小的字符串

> 原文:[https://www . geesforgeks . org/python-extract-range-size-strings/](https://www.geeksforgeeks.org/python-extract-range-sized-strings/)

有时，在处理大量数据时，我们可能会遇到一个问题，即需要提取特定范围大小的字符串。这种问题可能会在跨多个领域的验证案例中出现。让我们在 Python 字符串列表中讨论处理这个问题的特定方法。
**方法#1:使用列表理解+ len()**
上述功能的组合可用于执行此任务。在本例中，我们对所有字符串进行迭代，只返回使用 len()检查的范围大小的字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Range length Strings extraction
# using list comprehension + len()

# initialize list
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list
print("The original list : " + str(test_list))

# initialize i, j
i, j = 2, 3

# Range length Strings extraction
# using list comprehension + len()
res = [ele for ele in test_list if len(ele) >= i and len(ele) <= j]

# printing result
print("The range sized strings are : " + str(res))
```

**Output : **

```
The original list : ['gfg', 'is', 'best', 'for', 'geeks']
The range sized strings are : ['gfg', 'is', 'for']
```

**方法 2:使用 filter() + lambda**
上述功能的组合可用于执行此任务。在本例中，我们使用 filter()提取元素，逻辑在 lambda 函数中编译。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Range length Strings extraction
# using filter() + lambda

# initialize list
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list
print("The original list : " + str(test_list))

# initialize i, j
i, j = 2, 3

# Range length Strings extraction
# using filter() + lambda
res = list(filter(lambda ele: len(ele) >= i and len(ele) <= j, test_list))

# printing result
print("The range sized strings are : " + str(res))
```

**Output : **

```
The original list : ['gfg', 'is', 'best', 'for', 'geeks']
The range sized strings are : ['gfg', 'is', 'for']
```