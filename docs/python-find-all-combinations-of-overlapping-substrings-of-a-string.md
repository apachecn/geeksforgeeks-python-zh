# Python–查找字符串重叠子字符串的所有组合

> 原文:[https://www . geeksforgeeks . org/python-查找字符串的所有重叠子字符串组合/](https://www.geeksforgeeks.org/python-find-all-combinations-of-overlapping-substrings-of-a-string/)

给定一个字符串，任务是编写一个 Python 程序来查找一个字符串的所有重叠子字符串的组合，并将其存储在一个列表中。列表将按照子字符串的长度进行排序和分组。

> **输入:** test_str = 'Geeks4G '
> 
> **输出:** [["，"，"，"，"，"，"]，['G '，' e '，' k '，' s '，' 4 '，' G '，['Ge '，' ee '，' ek '，' ks '，' s4 '，' 4G']，['Geeks4 '，' eeks '，' eks4 '，' ks4G']，['Geeks '，' eeks4 '，' eks4G']，[' Geek S4 '，' eeks4G']
> 
> **说明**:提取所有长度重叠的子串。
> 
> **输入:** test_str = 'Geeks '
> 
> **输出:**[【g】、【e】、【e】、【k】、【s】、【Ge】、【ee】、【ek】、【ks】、【Gee】、【eek】、【eks】、【Geek】、【Geeks】、【geeks】
> 
> **解释:**提取所有长度重叠的子串。

**方法:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension/)*[*切片*](https://www.geeksforgeeks.org/string-slicing-in-python/) *和* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)*

*在本例中，我们使用切片来执行获取每个切片的任务，所有特定大小的字符串都是使用列表理解来创建的。所有大小的操作都是使用循环完成的。后来所有的都被打印成列表。*

***示例:***

## *蟒蛇 3*

```
*# Python3 code to demonstrate working of
# Overlapping substrings of all lengths
# Using list comprehension + slicing + loop

# initializing string
test_str = 'Geeks4G'

# printing original string
print("The original string is : " + str(test_str))

# manipulating overlap size using loop
res = []
for idx in range(len(test_str) + 1):

    # getting overlap strings
    res.append([test_str[j: j + idx] for j in range(len(test_str) - idx + 1)])

# printing result
print("All overlapping Strings : " + str(res))*
```

***输出:***

> *原来的字符串是:极客 4G*
> 
> *所有重叠字符串:[["，"，"，"，"，"，"，"，"，"]，['G '，' e '，' k '，' s '，' 4 '，' G']，['Ge '，' ee '，' ek '，' ks '，' s4 '，' 4G']，['Geek '，' eks '，' eeks '，' eks4 '，' ks4G']，['Geeks4 '，' eeks4G']，[' Geek 4G ']*