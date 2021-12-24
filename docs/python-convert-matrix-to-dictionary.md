# Python–将矩阵转换为字典

> 原文:[https://www . geesforgeks . org/python-convert-matrix-to-dictionary/](https://www.geeksforgeeks.org/python-convert-matrix-to-dictionary/)

给定一个矩阵，将其转换为字典，键作为行号，值作为嵌套列表。

> **输入** : test_list = [[5，6，7]，[8，3，2]]
> **输出** : {1: [5，6，7]，2: [8，3，2]}
> **解释**:矩阵行按顺序与行号配对。
> 
> **输入** : test_list = [[5，6，7]]
> **输出** : {1: [5，6，7]}
> **说明**:矩阵行按行号顺序配对。

**方法一:使用词典理解+范围()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用字典理解来执行迭代任务，并且 range()可用于执行行的编号。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert Matrix to dictionary 
# Using dictionary comprehension + range()

# initializing list
test_list = [[5, 6, 7], [8, 3, 2], [8, 2, 1]] 

# printing original list
print("The original list is : " + str(test_list))

# using dictionary comprehension for iteration
res = {idx + 1 : test_list[idx] for idx in range(len(test_list))}

# printing result 
print("The constructed dictionary : " + str(res))
```

**Output**

```py
The original list is : [[5, 6, 7], [8, 3, 2], [8, 2, 1]]
The constructed dictionary : {1: [5, 6, 7], 2: [8, 3, 2], 3: [8, 2, 1]}

```

**方法 2:使用词典理解+枚举()**

上述功能的组合可以用来解决这个问题。在这种情况下，字典理解有助于构造字典，枚举()有助于迭代，就像上述方法中的 range()一样。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert Matrix to dictionary 
# Using dictionary comprehension + enumerate()

# initializing list
test_list = [[5, 6, 7], [8, 3, 2], [8, 2, 1]] 

# printing original list
print("The original list is : " + str(test_list))

# enumerate used to perform assigning row number
res = {idx: val for idx, val in enumerate(test_list, start = 1)}

# printing result 
print("The constructed dictionary : " + str(res))
```

**Output**

```py
The original list is : [[5, 6, 7], [8, 3, 2], [8, 2, 1]]
The constructed dictionary : {1: [5, 6, 7], 2: [8, 3, 2], 3: [8, 2, 1]}

```