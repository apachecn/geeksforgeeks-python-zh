# Python–提取偶数长度字符串的行

> 原文:[https://www . geesforgeks . org/python-extract-带偶数长度字符串的行/](https://www.geeksforgeeks.org/python-extract-rows-with-even-length-strings/)

在本文中，我们有一个给定的矩阵，提取偶数长度的行。

> **输入**:test _ list =【【“gfg”、“is”、“best”】、【“best”、“good”、“geek”】、【“is”、“better”】、【“for”、“cs”】】
> **输出**:【【‘best’、‘good’、‘geek’】、【‘is’、‘better’】】
> **解释**:所有字符串长度均为偶数。
> **输入**:test _ list =[[“gfg”、“is”、“best”]、[“best”、“good”、“geeks”]、[“is”、“better”]、[“for”、“cs”]
> **输出**:[“is”、“better”]
> **解释**:所有字符串长度均为偶数。

**方法一:使用 all() +列表理解+ len()**

在这种情况下，我们检查每行中的所有字符串及其长度，并检查长度是否为偶数，如果行中的所有字符串长度为偶数，则将其添加到结果列表中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract rows with Even length strings
# Using all() + list comprehension + len()

# initializing list
test_list = [["gfg", "is", "best"], ["best", "good", "geek"], ["is", "better"], ["for", "cs"]]

# printing original list
print("The original list is : " + str(test_list))

# checking for all elements in row
res = [row for row in test_list if all(len(ele) % 2 == 0 for ele in row)]

# printing result 
print("Rows with even length : " + str(res))
```

**Output**

> 原列表为:[['gfg '，' is '，' best']，['best '，' good '，' geek']，['is '，' better']，['for '，' cs']]
> 偶数长度的行:['best '，' good '，' geek']，['is '，' better']]

**方法 2:使用滤镜()+λ+len()**

在这种情况下，我们使用 filter() + lambda，len()执行过滤任务，就像上面的方法一样，执行获取每个字符串长度的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract rows with Even length strings
# Using filter() + lambda + len()

# initializing list
test_list = [["gfg", "is", "best"], ["best", "good", "geek"], ["is", "better"], ["for", "cs"]]

# printing original list
print("The original list is : " + str(test_list))

# checking for all elements in row
# filtering done using filter() and lambda 
res = list(filter(lambda row : all(len(ele) % 2 == 0 for ele in row), test_list))

# printing result 
print("Rows with even length : " + str(res))
```

**Output**

> 原列表为:[['gfg '，' is '，' best']，['best '，' good '，' geek']，['is '，' better']，['for '，' cs']]
> 偶数长度的行:['best '，' good '，' geek']，['is '，' better']]