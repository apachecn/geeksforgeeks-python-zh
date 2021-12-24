# Python–根据列表

中第 Kth 键的值过滤字典

> 原文:[https://www . geesforgeks . org/python-filter-dictionary-by-values-in-kth-key-in-list/](https://www.geeksforgeeks.org/python-filter-dictionaries-by-values-in-kth-key-in-list/)

给定一个字典列表，任务是编写一个 Python 程序，根据列表中 Kth 键的元素过滤字典。

**示例:**

> **输入:**test _ list =[{“Gfg”:3，“是”:5，“最佳”:10}，
> 
> {“Gfg”:5，“是”:1，“最好”:1}，
> 
> {“Gfg”:8，“是”:3，“最好”:9}，
> 
> {“Gfg”:9，“is”:9，“best”:8 }，
> 
> {“Gfg”:4，“is”:10，“best”:7 }]，K =“best”，search_list = [1，9，8，4，5]
> 
> **输出:** [{'Gfg': 5，' is': 1，' best': 1}，{'Gfg': 8，' is': 3，' best': 9}，{'Gfg': 9，' is': 9，' best': 8}]
> 
> **说明:**省略了以“最佳”为关键字和 1、9、8、4、5 以外的值的字典。
> 
> **输入:**test _ list =[{“Gfg”:3，“是”:5，“最佳”:10}，
> 
> {“Gfg”:5，“是”:1，“最好”:1}，
> 
> {“Gfg”:8，“is”:3，“best”:9 }]，K =“best”，search_list = [1，9，4，5]
> 
> **输出:** [{'Gfg': 5，' is': 1，' best': 1}，{'Gfg': 8，' is': 3，' best': 9}]
> 
> **说明:**以“最佳”为关键字，省略 1、9、4、5 以外的值的字典。

**方法#1:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/) **+** [**条件语句**](https://www.geeksforgeeks.org/python-if-else/)

在这种情况下，在使用条件检查列表中的 Kth 键值后，键值对被添加到结果字典中，并使用循环进行迭代。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Filter dictionaries by values in Kth Key in list
# Using loop + conditional statements

# initializing list
test_list = [{"Gfg": 3, "is": 5, "best": 10},
             {"Gfg": 5, "is": 1, "best": 1},
             {"Gfg": 8, "is": 3, "best": 9},
             {"Gfg": 9, "is": 9, "best": 8},
             {"Gfg": 4, "is": 10, "best": 7}]

# printing original list
print("The original list is : " + str(test_list))

# initializing search_list
search_list = [1, 9, 8, 4, 5]

# initializing K
K = "best"

res = []
for sub in test_list:

    # checking if Kth key's value present in search_list
    if sub[K] in search_list:
        res.append(sub)

# printing result
print("Filtered dictionaries : " + str(res))
```

**输出:**

> 原始列表为:[{'Gfg': 3，' is': 5，' best': 10}，{'Gfg': 5，' is': 1，' best': 1}，{'Gfg': 8，' is': 3，' best': 9}，{'Gfg': 9，' is': 9，' best': 8}，{'Gfg': 4，' is': 10，' best': 7}]
> 
> 筛选字典:[{'Gfg': 5，' is': 1，' best': 1}，{'Gfg': 8，' is': 3，' best': 9}，{'Gfg': 9，' is': 9，' best': 8}]

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

类似于上面的方法，列表理解被用来为上面使用的方法提供速记。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Filter dictionaries by values in Kth Key in list
# Using list comprehension

# initializing list
test_list = [{"Gfg": 3, "is": 5, "best": 10},
             {"Gfg": 5, "is": 1, "best": 1},
             {"Gfg": 8, "is": 3, "best": 9},
             {"Gfg": 9, "is": 9, "best": 8},
             {"Gfg": 4, "is": 10, "best": 7}, ]

# printing original list
print("The original list is : " + str(test_list))

# initializing search_list
search_list = [1, 9, 8, 4, 5]

# initializing K
K = "best"

# list comprehension as shorthand for solving problem
res = [sub for sub in test_list if sub[K] in search_list]

# printing result
print("Filtered dictionaries : " + str(res))
```

**输出:**

> 原始列表为:[{'Gfg': 3，' is': 5，' best': 10}，{'Gfg': 5，' is': 1，' best': 1}，{'Gfg': 8，' is': 3，' best': 9}，{'Gfg': 9，' is': 9，' best': 8}，{'Gfg': 4，' is': 10，' best': 7}]
> 
> 筛选字典:[{'Gfg': 5，' is': 1，' best': 1}，{'Gfg': 8，' is': 3，' best': 9}，{'Gfg': 9，' is': 9，' best': 8}]