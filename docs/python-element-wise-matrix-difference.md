# Python-元素矩阵差异

> 原文:[https://www . geesforgeks . org/python-element-wise-matrix-difference/](https://www.geeksforgeeks.org/python-element-wise-matrix-difference/)

给定两个矩阵，任务是编写一个 Python 程序来执行元素差异。

**示例:**

> **输入** : test_list1 = [[2，4，5]，[5，4，2]，[1，2，3]]，test_list2 = [[6，4，6]，[9，6，3]，[7，5，4]]
> **输出** : [[4，0，1]，[4，2，1]，[6，3，1]]
> **解释**:6–2 = 4，4–4 = 0，6–5 等等。
> 
> **输入** : test_list1 = [[2，4，5]，[1，2，3]]，test_list2 = [[6，4，6]，[7，5，4]]
> **输出** : [[4，0，1]，[6，3，1]]
> **解释**:6–2 = 4，4–4 = 0，6–5 = 1。等等。

**方法#1:使用 loop +** [**zip()**](https://www.geeksforgeeks.org/zip-in-python/)

在本例中，我们使用 zip 执行合并行和行内索引的任务，嵌套循环用于遍历所有行的所有元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Element-wise Matrix Difference
# Using loop + zip()

# initializing lists
test_list1 = [[2, 4, 5], [5, 4, 2], [1, 2, 3]]
test_list2 = [[6, 4, 6], [9, 6, 3], [7, 5, 4]]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

res = []

# iterating for rows
for sub1, sub2 in zip(test_list1, test_list2):
    temp = []

    # iterate for elements
    for ele1, ele2 in zip(sub1, sub2):
        temp.append(ele2 - ele1)
    res.append(temp)

# printing result
print("The Matrix Difference : " + str(res))
```

**Output**

```
The original list 1 is : [[2, 4, 5], [5, 4, 2], [1, 2, 3]]
The original list 2 is : [[6, 4, 6], [9, 6, 3], [7, 5, 4]]
The Matrix Difference : [[4, 0, 1], [4, 2, 1], [6, 3, 1]]
```

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)**+**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)

在本文中，我们使用 zip()执行压缩任务，并使用列表理解以一种线性方式解决这个问题。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Element-wise Matrix Difference
# Using loop + zip()

# initializing lists
test_list1 = [[2, 4, 5], [5, 4, 2], [1, 2, 3]]
test_list2 = [[6, 4, 6], [9, 6, 3], [7, 5, 4]]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# using list comprehension to perform task in one line
res = [[ele2 - ele1 for ele1, ele2 in zip(sub1, sub2)]
       for sub1, sub2 in zip(test_list1, test_list2)]

# printing result
print("The Matrix Difference : " + str(res))
```

**Output**

```
The original list 1 is : [[2, 4, 5], [5, 4, 2], [1, 2, 3]]
The original list 2 is : [[6, 4, 6], [9, 6, 3], [7, 5, 4]]
The Matrix Difference : [[4, 0, 1], [4, 2, 1], [6, 3, 1]]
```