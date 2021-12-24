# Python–为值列表字典中的列表元素分配键值

> 原文:[https://www . geesforgeks . org/python-赋值-键值-列表-元素-从值-列表-字典/](https://www.geeksforgeeks.org/python-assigning-key-values-to-list-elements-from-value-list-dictionary/)

给定元素列表，用值列表中匹配值的键映射它们。

> **输入** : test_list = [4，6，3，5，3]，test _ dict = {“Gfg”:[5，3，6]，“is”:[8，4]}
> **输出**:[‘is’，‘Gfg’，‘Gfg’，‘Gfg’]
> **解释** : 4 存在于“is”键中，因此映射到新列表中。
> 
> **输入** : test_list = [6，3，5，3]，test_dict = {"Gfg" : [5，3，6]，" is" : [18，14]}
> **输出** : ['Gfg '，' Gfg '，' Gfg']
> **解释**:所有存在于“Gfg”键中的元素。

**方法一:使用列表理解**

这是执行这项任务的方法之一。在这种情况下，我们提取字典值列表的每个元素来检查列表值的出现，如果匹配，我们将该键的值分配给该索引。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Assigning Key values to list elements from Value list Dictionary
# Using list comprehension

# initializing list
test_list = [4, 6, 3, 10, 5, 3]

# printing original list
print("The original list : " + str(test_list))

# initializing dictionary 
test_dict = {"Gfg" : [5, 3, 6], "is" : [8, 4], "Best" : [10, 11]}

# nested loop inside list comprehension to check each key 
res = [key for ele in test_list
       for key, val in test_dict.items() if ele in val]

# printing result 
print("The filtered list : " + str(res))
```

**Output**

```py
The original list : [4, 6, 3, 10, 5, 3]
The filtered list : ['is', 'Gfg', 'Gfg', 'Best', 'Gfg', 'Gfg']

```

**方法二:使用词典理解+列表理解**

这是执行这项任务的另一种方式。在本例中，我们创建了反向字典，并将每个列表值与其关键字进行映射，并声明每个关键字都与参数关键字列表元素进行映射，以匹配关键字值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Assigning Key values to list elements from Value list Dictionary
# Using dictionary comprehension + list comprehension

# initializing list
test_list = [4, 6, 3, 10, 5, 3]

# printing original list
print("The original list : " + str(test_list))

# initializing dictionary 
test_dict = {"Gfg" : [5, 3, 6], "is" : [8, 4], "Best" : [10, 11]}

# creating inverse dictionary of elements 
temp = {j : i for i, k in test_dict.items() for j in k}

# creating end result by mapping elements
res = [temp.get(key) for key in test_list]

# printing result 
print("The filtered list : " + str(res))
```

**Output**

```py
The original list : [4, 6, 3, 10, 5, 3]
The filtered list : ['is', 'Gfg', 'Gfg', 'Best', 'Gfg', 'Gfg']

```