# Python–求给定索引下字符串长度的总和

> 原文:[https://www . geesforgeks . org/python-在给定索引处查找字符串长度总和/](https://www.geeksforgeeks.org/python-find-the-sum-of-length-of-strings-at-given-indices/)

给定字符串列表，编写一个 Python 程序来计算列表自定义索引的长度总和。

**示例:**

> **输入**:test _ list =[“gfg”、“is”、“best”、“for”、“geeks”]，idx_list = [0，1，4]
> **输出** : 10
> **解释** : 3 + 2 + 5 = 10。(idx 的字符串大小。)
> 
> **输入**:test _ list =[“gfg”、“is”、“best”、“for”、“geeks”]，idx_list = [0，2，4]
> **输出** : 12
> **解释** : 3 + 4 + 5 = 12。

**方法#1:使用**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+loop**

在这种情况下，我们对所有索引进行迭代，并检查它们是否出现在索引列表中，如果出现，则增加求和计数器中的频率。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Length sum of custom indices Strings
# Using len() + loop

# initializing list
test_list = ["gfg", "is", "best", "for", "geeks"]

# printing original lists
print("The original list is : " + str(test_list))

# initializing idx list
idx_list = [0, 1, 4]

res = 0
for idx, ele in enumerate(test_list):

    # adding length if index in idx_list
    if idx in idx_list:
        res += len(ele)

# printing result
print("Computed Strings lengths sum : " + str(res))
```

**Output**

```py
The original list is : ['gfg', 'is', 'best', 'for', 'geeks']
Computed Strings lengths sum : 10
```

**方法 2:使用** [**求和()**](https://www.geeksforgeeks.org/sum-function-python/)**+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在本例中，我们使用 sum()执行求和任务，其余所有功能都按照上述方法执行，就像一行代码一样。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Length sum of custom indices Strings
# Using sum() + len() + list comprehension

# initializing list
test_list = ["gfg", "is", "best", "for", "geeks"]

# printing original lists
print("The original list is : " + str(test_list))

# initializing idx list
idx_list = [0, 1, 4]

# performing summation using sum()
# len() used to get strings lengths
res = sum([len(ele) for idx, ele in enumerate(test_list) if idx in idx_list])

# printing result
print("Computed Strings lengths sum : " + str(res))
```

**Output**

```py
The original list is : ['gfg', 'is', 'best', 'for', 'geeks']
Computed Strings lengths sum : 10
```