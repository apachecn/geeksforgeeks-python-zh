# Python–过滤无空格字符串的行

> 原文:[https://www . geesforgeks . org/python-filter-row-不带空格-strings/](https://www.geeksforgeeks.org/python-filter-rows-without-space-strings/)

给定矩阵，提取字符串中没有空格的行。

**示例:**

> **输入**:test _ list =[[“gfg 是”、“最好的”]、[“gfg”、“好的”]、[“gfg 很酷”]、[“爱”、“gfg”]]
> **输出**:[‘gfg’，‘好的’]、[‘爱’，‘gfg’]]
> **解释**:两个列表都有字符串没有空格。
> 
> **输入**:test _ List =[[“gfg 是”、“最好”]、[“gfg”、“好”]、[“gfg 是酷”]、[“爱”、“gfg”]]
> **输出**:[“‘爱’、‘gfg’]
> **解释** : List 有字符串没有空格。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) **+** [**任意()**](https://www.geeksforgeeks.org/any-all-in-python/)**+**[**regex**](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

在这种情况下，我们使用正则表达式检查每个字符串中是否没有空格，使用 any()检查是否有空格，该行不会被添加。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Filter rows without Space Strings
# Using list comprehension + any() + regex
import re

# initializing list
test_list = [["gfg is", "best"], ["gfg", "good"],
             ["gfg is cool"], ["love", "gfg"]]

# printing original list
print("The original list is : " + str(test_list))

# checking for spaces using regex
# not including row if any string has space
res = [row for row in test_list if not any(
    bool(re.search(r"\s", ele)) for ele in row)]

# printing result
print("Filtered Rows : " + str(res))
```

**输出:**

> 原列表为:[['gfg is '，' best']，['gfg '，' good']，['gfg is cool']，['love '，' gfg']]
> 过滤行:['gfg '，' good']，['love '，' gfg']]

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**lambda**](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)**+any()+regex**

在本例中，我们使用 filter()和 lambda 函数执行过滤任务，其余所有功能都与上述方法类似。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Filter rows without Space Strings
# Using filter() + lambda + any() + regex
import re

# initializing list
test_list = [["gfg is", "best"], ["gfg", "good"],
             ["gfg is cool"], ["love", "gfg"]]

# printing original list
print("The original list is : " + str(test_list))

# checking for spaces using regex
# not including row if any string has space
res = list(filter(lambda row: not any(bool(re.search(r"\s", ele))
                                      for ele in row), test_list))

# printing result
print("Filtered Rows : " + str(res))
```

**输出:**

> 原列表为:[['gfg is '，' best']，['gfg '，' good']，['gfg is cool']，['love '，' gfg']]
> 过滤行:['gfg '，' good']，['love '，' gfg']]