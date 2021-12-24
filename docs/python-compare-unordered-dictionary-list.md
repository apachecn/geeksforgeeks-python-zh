# Python–比较无序字典列表

> 原文:[https://www . geesforgeks . org/python-compare-无序-字典-列表/](https://www.geeksforgeeks.org/python-compare-unordered-dictionary-list/)

有时，在使用记录时，我们可能会遇到需要在记录之间进行比较的问题。如果它们相等或不相等，这可以是字典列表的类型。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`"=="`运算符(仅键无序)**
对于只有字典的键无序，列表中的排序方式正确的情况，可以使用“==”运算符进行测试。

```py
# Python3 code to demonstrate working of 
# Compare Unordered Dictionary List
# Using "==" operator

# initializing lists
test_list1 = [{'Manjeet' : 12, 'Himani' : 15}, {'Akshat' : 20, 'Vashu' : 15}]
test_list2 = [{'Himani' : 15, 'Manjeet' : 12}, {'Vashu' : 15, 'Akshat' : 20}]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Compare Unordered Dictionary List
# Using "==" operator
res = test_list1 == test_list2

# printing result 
print("Are Dictionary Lists equal ? : " + str(res)) 
```

**Output :**

> 原列表 1 为:[{'Himani': 15，' Manjeet': 12}，{'Akshat': 20，' Vashu': 15}]
> 原列表 2 为:[{'Himani': 15，' Manjeet': 12}，{'Vashu': 15，' Akshat': 20}]
> 字典列表是否相等？:真