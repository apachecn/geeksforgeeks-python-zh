# Python–阈值大小以上的过滤器字符串

> 原文:[https://www . geesforgeks . org/python-filter-threshold-size-strings/](https://www.geeksforgeeks.org/python-filter-above-threshold-size-strings/)

有时，在处理大量数据时，我们可能会遇到一个问题，即我们需要提取的只是特定大小的、超过最小阈值的字符串。这种问题可能会在跨多个领域的验证案例中出现。让我们在 Python 字符串列表中讨论处理这个问题的特定方法。

**方法#1:使用列表理解+ `len()`**
上述功能的组合可用于执行该任务。在本例中，我们对所有字符串进行迭代，只返回使用 len()检查的阈值以上的字符串。

```
# Python3 code to demonstrate working of
# Filter above Threshold size Strings
# using list comprehension + len()

# initialize list 
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list 
print("The original list : " + str(test_list))

# initialize Threshold
thres = 4

# Filter above Threshold size Strings
# using list comprehension + len()
res = [ele for ele in test_list if len(ele) >= thres]

# printing result
print("The above Threshold size strings are : " + str(res))
```

**Output :**

```
The original list : ['gfg', 'is', 'best', 'for', 'geeks']
The above Threshold size strings are : ['best', 'geeks']

```