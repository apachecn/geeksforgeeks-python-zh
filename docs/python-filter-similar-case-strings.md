# Python–过滤相似案例字符串

> 原文:[https://www . geesforgeks . org/python-filter-相似大小写-strings/](https://www.geeksforgeeks.org/python-filter-similar-case-strings/)

给定字符串列表，任务是编写一个 Python 程序来过滤所有大小写相似的字符串，无论是大写还是小写。

**示例:**

> **输入**:test _ list =[“GFG”、“Geeks”、“best”、“FOr”、“all”、“Geeks”]
> **输出**:[‘GFG’、‘best’、‘all’、‘Geeks’]
> **解释** : GFG 全大写，best 全小写。
> 
> **输入**:test _ list =[“GFG”、“极客”、“最佳”]
> **输出**:[‘GFG’，‘最佳’]
> **说明** : GFG 全大写，最佳全小写。

**方法一:使用**[**is lower()**](https://www.geeksforgeeks.org/python-string-islower-method/)**+**[**is upper()**](https://www.geeksforgeeks.org/python-string-isupper-method/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在本文中，我们使用 islower()和 isupper()检查每个字符串是小写还是大写，并使用列表理解来遍历字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Filter Similar Case Strings
# Using islower() + isupper() + list comprehension

# initializing Matrix
test_list = ["GFG", "Geeks", 
             "best", "FOr", "all", "GEEKS"]

# printing original list
print("The original list is : " + str(test_list))

# islower() and isupper() used to check for cases
res = [sub for sub in test_list if sub.islower() or sub.isupper()]

# printing result
print("Strings with same case : " + str(res))
```

**输出:**

> 原列表为:['GFG '，' Geeks '，' best '，' FOr '，' all '，' GEEKS']
> 大小写相同的字符串:['GFG '，' best '，' all '，' GEEKS']

**方法 2:使用**[**is lower()**](https://www.geeksforgeeks.org/python-string-islower-method/)**+**[**is upper()**](https://www.geeksforgeeks.org/python-string-isupper-method/)**+**[**filter()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[T21】lambda](https://www.geeksforgeeks.org/python-lambda/)

在本文中，我们使用 filter()和 lambda 函数来执行过滤字符串的任务。Rest 的所有功能都类似于上面的方法。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Filter Similar Case Strings
# Using islower() + isupper() + filter() + lambda

# initializing Matrix
test_list = ["GFG", "Geeks", "best",
             "FOr", "all", "GEEKS"]

# printing original list
print("The original list is : " + str(test_list))

# islower() and isupper() used to check for cases
# filter() and lambda function used for filtering
res = list(filter(lambda sub : sub.islower() or sub.isupper(), test_list))

# printing result
print("Strings with same case : " + str(res))
```

**输出:**

> 原列表为:['GFG '，' Geeks '，' best '，' FOr '，' all '，' GEEKS']
> 大小写相同的字符串:['GFG '，' best '，' all '，' GEEKS']