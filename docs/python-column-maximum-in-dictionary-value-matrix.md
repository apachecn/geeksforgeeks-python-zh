# Python–字典值矩阵中的列最大值

> 原文:[https://www . geesforgeks . org/python-column-最大字典值-matrix/](https://www.geeksforgeeks.org/python-column-maximum-in-dictionary-value-matrix/)

给定一个带有矩阵值的字典，计算这些矩阵的每一列的最大值。

```
Input  :  test_dict = {"Gfg" : [[7, 6], [3, 2]],
                                        "is" : [[3, 6], [6, 10]],
                                        "best" : [[5, 8], [2, 3]]}
Output : {'Gfg': [7, 6], 'is': [6, 10], 'best': [5, 8]}
Explanation :  7 > 3, 6 > 2, hence ordering.

Input  :  test_dict = {"Gfg" : [[7, 6], [3, 2]],
                                        "is" : [[3, 6], [6, 10]]}
Output : {'Gfg': [7, 6], 'is': [6, 10]}
Explanation :  6 > 3, 10 > 6, hence ordering.

```

**方法一:使用词典理解+排序()+条目()**

这是执行这项任务的方法之一。在这种情况下，内部列被提取并排序，排序列表的最后一个值(最大值)作为结果返回。使用字典理解的所有列表值都会出现这种情况。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Column Maximums of Dictionary Value Matrix
# Using dictionary comprehension + sorted() + items()

# initializing dictionary
test_dict = {"Gfg" : [[5, 6], [3, 4]],
            "is" : [[4, 6], [6, 8]],
            "best" : [[7, 4], [2, 3]]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# sorted() used to sort and "-1" used to get last i.e
# maximum element
res = {key : sorted(val, key = lambda ele : (ele[0], ele[1]))[-1] for key, val in test_dict.items()}

# printing result
print("The evaluated dictionary : " + str(res))
```

**Output**

```
The original dictionary is : {'Gfg': [[5, 6], [3, 4]], 'is': [[4, 6], [6, 8]], 'best': [[7, 4], [2, 3]]}
The evaluated dictionary : {'Gfg': [5, 6], 'is': [6, 8], 'best': [7, 4]}

```

**方法 2:使用 max() + map() + zip()**

这是完成这项任务的方法之一。在这种情况下，我们使用 max()提取最大值，并使用 zip()将列与列表对齐，使用 map()将 zip 的逻辑扩展到每一列。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Column Maximums of Dictionary Value Matrix
# Using max() + map() + zip()

# initializing dictionary
test_dict = {"Gfg" : [[5, 6], [3, 4]],
            "is" : [[4, 6], [6, 8]],
            "best" : [[7, 4], [2, 3]]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# map extending logic to entire columns
# result compiled using dictionary comprehension
res = {key: list(map(max, zip(*val))) for key, val in test_dict.items()}

# printing result
print("The evaluated dictionary : " + str(res))
```

**Output**

```
The original dictionary is : {'Gfg': [[5, 6], [3, 4]], 'is': [[4, 6], [6, 8]], 'best': [[7, 4], [2, 3]]}
The evaluated dictionary : {'Gfg': [5, 6], 'is': [6, 8], 'best': [7, 4]}

```