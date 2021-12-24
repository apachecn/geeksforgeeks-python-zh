# Python–在 ASCII 范围内过滤字符串

> 原文:[https://www . geesforgeks . org/python-filter-strings-in-ascii-range/](https://www.geeksforgeeks.org/python-filter-strings-within-ascii-range/)

给定 ASCII 或字母范围，过滤特定范围内的字符串。

> **输入**:test _ list =【“gfg”“is”“best”“for”“geeks”】，strt_asc，end_asc = 105，115
> **输出**:【‘is’】
> **解释** : i 有 105，s 有 115，在 ASCII 值范围内。
> **输入**:test _ list =[“gfg”，“is”，“best”，“for”，“geeks”]，strt_asc，end_asc = 100，115
> **输出**:[“gfg”，“is”，“for”，“geeks”]
> **解释**:包含范围字符的字符串。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**全部()**](https://www.geeksforgeeks.org/any-all-in-python/) **+** [**顺序()**](https://www.geeksforgeeks.org/ord-function-python/)

在这种情况下，我们检查所有字符是否在给定的 ASCII 范围内，使用 order()计算，并相应地过滤字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Filter Strings within ASCII range
# Using list comprehension + ord() + all()

# initializing list
test_list = ["gfg", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing ASCII range
strt_asc, end_asc = 105, 115

# checking for all characters to be in ASCII range
res = [sub for sub in test_list if all(
    ord(ele) >= strt_asc and ord(ele) <= end_asc for ele in sub)]

# printing result
print("Filtered Strings : " + str(res))
```

**Output**

```
The original list is : ['gfg', 'is', 'best', 'for', 'geeks']
Filtered Strings : ['is']

```

**方法 2:使用过滤器()+λ+all()+order()**

在本例中，我们使用 filter()和 lambda 函数执行过滤任务，order()和 all()的使用方式与上述方法类似。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Filter Strings within ASCII range
# Using filter() + lambda + all() + ord()

# initializing list
test_list = ["gfg", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing ASCII range
strt_asc, end_asc = 105, 115

# checking for all characters to be in ASCII range
res = list(filter(lambda sub: all(ord(ele) >= strt_asc and ord(
    ele) <= end_asc for ele in sub), test_list))

# printing result
print("Filtered Strings : " + str(res))
```

**Output**

```
The original list is : ['gfg', 'is', 'best', 'for', 'geeks']
Filtered Strings : ['is']

```