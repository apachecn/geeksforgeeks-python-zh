# Python–将坐标字典转换为矩阵

> 原文:[https://www . geesforgeks . org/python-convert-coordinate-dictionary-to-matrix/](https://www.geeksforgeeks.org/python-convert-coordinate-dictionary-to-matrix/)

有时，在使用 Python Matrix 时，我们会遇到这样的问题，即我们有字典记录，其中关键字作为矩阵位置及其值，我们希望将其转换为实际的 Matrix。这在许多领域都有应用，包括竞争性编程和日常编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+ `max()` +列表理解**
以上方法的组合可以用来解决这个问题。在本文中，我们使用 max()来获取矩阵的维数，使用列表理解来创建矩阵，并使用循环来赋值。

```py
# Python3 code to demonstrate working of 
# Convert Coordinate Dictionary to Matrix
# Using loop + max() + list comprehension

# initializing dictionary
test_dict = { (0, 1) : 4, (2, 2) : 6, (3, 1) : 7, (1, 2) : 10, (3, 2) : 11}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Convert Coordinate Dictionary to Matrix
# Using loop + max() + list comprehension
temp_x = max([cord[0] for cord in test_dict.keys()])
temp_y = max([cord[1] for cord in test_dict.keys()])
res = [[0] * (temp_y + 1) for ele in range(temp_x + 1)]

for (i, j), val in test_dict.items():
    res[i][j] = val

# printing result 
print("The dictionary after creation of Matrix : " + str(res)) 
```

**Output :**

> 原字典为:{(0，1): 4，(1，2): 10，(3，2): 11，(3，1): 7，(2，2): 6}
> 矩阵创建后的字典:[[0，4，0]，[0，0，10]，[0，0，6]，[0，7，11]]