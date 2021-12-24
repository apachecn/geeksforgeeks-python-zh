# Python–将整数矩阵转换为字符串矩阵

> 原文:[https://www . geesforgeks . org/python-convert-integer-matrix-to-string-matrix/](https://www.geeksforgeeks.org/python-convert-integer-matrix-to-string-matrix/)

给定一个包含整数值的矩阵，将每个元素转换为字符串。

> **输入** : test_list = [[4，5，7]，[10，8，3]，[19，4，6]]
> **输出** : [['4 '，' 5 '，' 7']，['10 '，' 8 '，' 3']，['19 '，' 4 '，' 6 ']
> **解释**:矩阵所有元素转换为字符串。
> 
> **输入** : test_list = [[4，5，7]，[10，8，3]]
> **输出** : [['4 '，' 5 '，' 7']，['10 '，' 8 '，' 3 ']
> **解释**:矩阵所有元素转换为字符串。

**方法一:使用 str() +列表理解**

上述方法的结合可以用来解决这个问题。在本例中，我们使用 str()执行转换，列表理解用于迭代所有元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert Integer Matrix to String Matrix
# Using str() + list comprehension

# initializing list
test_list = [[4, 5, 7], [10, 8, 3], [19, 4, 6], [9, 3, 6]]

# printing original list
print("The original list : " + str(test_list))

# using str() to convert each element to string 
res = [[str(ele) for ele in sub] for sub in test_list]

# printing result 
print("The data type converted Matrix : " + str(res))
```

**Output**

```py
The original list : [[4, 5, 7], [10, 8, 3], [19, 4, 6], [9, 3, 6]]
The data type converted Matrix : [['4', '5', '7'], ['10', '8', '3'], ['19', '4', '6'], ['9', '3', '6']]

```

**方法 2:使用 str() + map()**

上述功能的组合也可以用来解决这个问题。在本文中，我们使用 map()将字符串转换扩展到所有行元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert Integer Matrix to String Matrix
# Using str() + map()

# initializing list
test_list = [[4, 5, 7], [10, 8, 3], [19, 4, 6], [9, 3, 6]]

# printing original list
print("The original list : " + str(test_list))

# using map() to extend all elements as string  
res = [list(map(str, sub)) for sub in test_list]

# printing result 
print("The data type converted Matrix : " + str(res))
```

**Output**

```py
The original list : [[4, 5, 7], [10, 8, 3], [19, 4, 6], [9, 3, 6]]
The data type converted Matrix : [['4', '5', '7'], ['10', '8', '3'], ['19', '4', '6'], ['9', '3', '6']]

```