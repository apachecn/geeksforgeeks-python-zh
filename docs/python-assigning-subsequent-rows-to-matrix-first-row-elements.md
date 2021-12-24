# Python–将后续行分配给矩阵第一行元素

> 原文:[https://www . geesforgeks . org/python-赋值-后续-行-矩阵-第一行-元素/](https://www.geeksforgeeks.org/python-assigning-subsequent-rows-to-matrix-first-row-elements/)

给定一个(N + 1) * N 矩阵，分配矩阵第一行的每一列，即矩阵的下一行。

> **输入** : test_list = [[5，8，10]，[2，0，9]，[5，4，2]，[2，3，9]]
> **输出** : {5: [2，0，9]，8: [5，4，2]，10: [2，3，9]}
> **解释** : 5 与第二排配对，8 与第三排配对，10 与第四排配对
> 
> **输入** : test_list = [[5，8]，[2，0]，[5，4]]
> **输出** : {5: [2，0]，8: [5，4]}
> **解释** : 5 配第二排，8 配第三排。

**方法一:利用词典理解**

这是执行这项任务的方法之一。在这种情况下，我们使用循环迭代行和相应的列，并使用字典理解以单行方式相应地分配值列表。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Assigning Subsequent Rows to Matrix first row elements
# Using dictionary comprehension

# initializing list
test_list = [[5, 8, 9], [2, 0, 9], [5, 4, 2], [2, 3, 9]]

# printing original list
print("The original list : " + str(test_list))

# pairing each 1st col with next rows in Matrix
res = {test_list[0][ele] :  test_list[ele + 1] for ele in range(len(test_list) - 1)}

# printing result 
print("The Assigned Matrix : " + str(res))
```

**Output**

```
The original list : [[5, 8, 9], [2, 0, 9], [5, 4, 2], [2, 3, 9]]
The Assigned Matrix : {5: [2, 0, 9], 8: [5, 4, 2], 9: [2, 3, 9]}

```

**方法 2:使用 zip() +列表切片+ dict()**

这是执行这项任务的另一种方式。在本例中，我们使用列表切片将元素切片为第一行和后续行，zip()执行所需的分组任务。归来的

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Assigning Subsequent Rows to Matrix first row elements
# Using zip() + list slicing + dict()

# initializing list
test_list = [[5, 8, 9], [2, 0, 9], [5, 4, 2], [2, 3, 9]]

# printing original list
print("The original list : " + str(test_list))

# dict() to convert back to dict type 
# slicing and pairing using zip() and list slicing
res = dict(zip(test_list[0], test_list[1:]))

# printing result 
print("The Assigned Matrix : " + str(res))
```

**Output**

```
The original list : [[5, 8, 9], [2, 0, 9], [5, 4, 2], [2, 3, 9]]
The Assigned Matrix : {5: [2, 0, 9], 8: [5, 4, 2], 9: [2, 3, 9]}

```