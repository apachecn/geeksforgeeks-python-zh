# Python–过滤超序列字符串

> 原文:[https://www . geesforgeks . org/python-filter-super quence-strings/](https://www.geeksforgeeks.org/python-filter-supersequence-strings/)

给定一个字符串列表和子字符串，任务是编写一个 Python 程序来提取所有字符串，这些字符串包含了可以用来生成子字符串的所有字符。

**示例:**

> **输入:**test _ list =[“gfg”、“/”、“geeksforgeeks”、“best”、“for”、“geeks”]，substr =“kgs”
> 
> **输出:** [“极客”“极客”]
> 
> **说明:**两个字符串中都存在所有 kgs 字符。
> 
> **输入:**test _ list =[“gfg”、“/”、“geeksforgeeks”、“best”、“for”、“geeks”]，substr =“kgf”
> 
> **输出** : [“极客 forgeeks”]
> 
> **说明:**所有 kgs 字符只出现在 geeksforgeeks 字符串中。

**方法一:使用**[**all()**](https://www.geeksforgeeks.org/any-all-in-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在本例中，我们使用 all()检查字符串中的所有字符。字符串的迭代是使用列表理解完成的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Filter Supersequence Strings
# Using all() + list comprehension

# initializing list
test_list = ["gfg", "/", "geeksforgeeks", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing substr
substr = "kgs"

# all() checks for all characters in strings
res = [sub for sub in test_list if all(ele in sub for ele in substr)]

# printing result
print("Filtered strings : " + str(res))
```

**输出:**

> 最初的名单是:['gfg '，'/'，' geeksforgeeks '，' best '，' for '，' geeks']
> 
> 过滤后的字符串:[' geeks forgeek '，' geeks']

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/) **+ all()**

在这种情况下，我们使用 filter()和 lambda 函数执行过滤任务，而不是在 upper 方法中使用列表理解和条件。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Filter Supersequence Strings
# Using filter() + all()

# initializing list
test_list = ["gfg", "/", "geeksforgeeks", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing substr
substr = "kgs"

# all() checks for all characters in strings
res = list(filter(lambda sub: all(ele in sub for ele in substr), test_list))

# printing result
print("Filtered strings : " + str(res))
```

**输出:**

> 最初的名单是:['gfg '，'/'，' geeksforgeeks '，' best '，' for '，' geeks']
> 
> 过滤后的字符串:[' geeks forgeek '，' geeks']