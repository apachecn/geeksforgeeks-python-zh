# Python–矩阵中列到字典的转换

> 原文:[https://www . geesforgeks . org/python-columns-to-dictionary-conversion-in-matrix/](https://www.geeksforgeeks.org/python-columns-to-dictionary-conversion-in-matrix/)

给定一个矩阵，转换为字典，第一行中的元素作为键，后续行作为值列表。

> **输入** : test_list = [[4，5，7]，[10，8，4]，[19，4，6]，[9，3，6]]
> ]**输出** : {4: [10，19，9]，5: [8，4，3]，7: [4，6，6]}
> **说明:**所有列映射第 1 行元素。例 4 - > 10，19，9。
> 
> **输入** : test_list = [[4，5，7]，[10，8，4]，[19，4，6]，[9，3，7]]
> ]**输出** : {4: [10，19，9]，5: [8，4，3]，7: [4，6，7]}
> **解释**:所有列映射第一行元素。7 - > 4，6，7。

**方法一:使用列表理解+词典理解**

这是执行这项任务的方法之一。在这种情况下，列表理解负责值的构造和映射，字典转换使用字典理解来完成。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Columns to Dictionary Conversion in Matrix
# Using dictionary comprehension + list comprehension

# initializing list
test_list = [[4, 5, 7], [10, 8, 3], [19, 4, 6], [9, 3, 6]]

# printing original list
print("The original list : " + str(test_list))

# dictionary comprehension performing re making of result 
# dictionary
res = {test_list[0][idx]: [test_list[ele][idx]
      for ele in range(1, len(test_list))]
      for idx in range(len(test_list[0]))}

# printing result 
print("Reformed dictionary : " + str(res))
```

**Output**

```py
The original list : [[4, 5, 7], [10, 8, 3], [19, 4, 6], [9, 3, 6]]
Reformed dictionary : {4: [10, 19, 9], 5: [8, 4, 3], 7: [3, 6, 6]}

```

**方法 2:使用词典理解+ zip()**

这是解决这个问题的另一种方法。在这种情况下，我们使用 zip()将所有列元素相互映射，并使用字典理解来执行字典的重映射。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Columns to Dictionary Conversion in Matrix
# Using dictionary comprehension + zip()

# initializing list
test_list = [[4, 5, 7], [10, 8, 3], [19, 4, 6], [9, 3, 6]]

# printing original list
print("The original list : " + str(test_list))

# appropriate slicing before zip function 
res = {ele[0]: list(ele[1:]) for ele in zip(*test_list)}

# printing result 
print("Reformed dictionary : " + str(res))
```

**Output**

```py
The original list : [[4, 5, 7], [10, 8, 3], [19, 4, 6], [9, 3, 6]]
Reformed dictionary : {4: [10, 19, 9], 5: [8, 4, 3], 7: [3, 6, 6]}

```