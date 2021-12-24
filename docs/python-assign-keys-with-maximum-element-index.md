# Python–使用最大元素索引分配键

> 原文:[https://www . geesforgeks . org/python-assign-keys-with-maximum-element-index/](https://www.geeksforgeeks.org/python-assign-keys-with-maximum-element-index/)

给定带有值列表的字典，任务是编写一个 Python 程序，为每个键分配值列表中最大值的索引。

**示例:**

> **输入:**test _ dict = {“gfg”:[5，3，6，3]，“is”:[1，7，5，3]，“best”:[9，1，3，5]}
> 
> **输出:** {'gfg': 2，' is': 1，' best': 0}
> 
> **说明:**在第二个索引处，“gfg”值中的 Max 元素为 6，因此被指定为 2。
> 
> **输入:**test _ dict = {“gfg”:[9，3，6，3]，“is”:[1，7，5，3]，“best”:[9，1，3，5]}
> 
> **输出:** {'gfg': 0，' is': 1，' best': 0}
> 
> **说明:**第 0 个索引处“gfg”值中的 Max 元素为 9，因此被赋值为 0。

**方法#1:使用**[**max()**](https://www.geeksforgeeks.org/max-min-python/)**+loop+**[**index()**](https://www.geeksforgeeks.org/python-list-index/)

在本例中，我们使用 max()和 index()从值列表中获取最大元素的索引。循环用于字典中键的迭代任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Assign keys with Maximum element index
# Using max() + index() + loop

# initializing dictionary
test_dict = {"gfg": [5, 3, 6, 3], "is": [1, 7, 5, 3], "best": [9, 1, 3, 5]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

res = dict()
for key in test_dict:

    # using index() to get required value
    res[key] = test_dict[key].index(max(test_dict[key]))

# printing result
print("The maximum index assigned dictionary : " + str(res))
```

**输出:**

> 原始字典为:{'gfg': [5，3，6，3]，' is': [1，7，5，3]，' best': [9，1，3，5]}
> 
> 分配给字典的最大索引:{“gfg”:2，“is”:1，“best”:0 }

**方法 2:使用词典理解+ max() + index()**

在本文中，我们使用上述方法的字典理解速记变体来执行获取结果的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Assign keys with Maximum element index
# Using dictionary comprehension + max() + index()

# initializing dictionary
test_dict = {"gfg": [5, 3, 6, 3], "is": [1, 7, 5, 3], "best": [9, 1, 3, 5]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using dictionary comprehension as one liner alternative
res = {key: test_dict[key].index(max(test_dict[key])) for key in test_dict}

# printing result
print("The maximum index assigned dictionary : " + str(res))
```

**输出:**

> 原始字典为:{'gfg': [5，3，6，3]，' is': [1，7，5，3]，' best': [9，1，3，5]}
> 
> 分配给字典的最大索引:{“gfg”:2，“is”:1，“best”:0 }