# 在 Python 中给矩阵添加自定义边框

> 原文:[https://www . geesforgeks . org/add-custom-borders-to-matrix-in-python/](https://www.geeksforgeeks.org/add-custom-borders-to-matrix-in-python/)

给定一个矩阵，任务是编写一个 python 程序来打印具有自定义边框的每一行。

```py
Input : test_list = [[4, 5, 6], [1, 4, 5], [6, 9, 1], [0, 3 ,1]], bord = "|"
Output : | 4 5 6 |
         | 1 4 5 |
         | 6 9 1 |
         | 0 3 1 |
Explanation : Matrix is ended using | border as required.

Input : test_list = [[4, 5, 6], [1, 4, 5], [6, 9, 1], [0, 3 ,1]], bord = "!"
Output : ! 4 5 6 !
         ! 1 4 5 !
         ! 6 9 1 !
         ! 0 3 1 !
Explanation : Matrix is ended using ! border as required.
```

**方法#1:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在本例中，我们使用由空格分隔的内部循环来执行打印行元素的任务。添加自定义边框的主要步骤是使用+运算符连接。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Custom Matrix Borders
# Using loop

# initializing list
test_list = [[4, 5, 6], [1, 4, 5], 
             [6, 9, 1], [0, 3, 1]]

# printing original list
print("The original list is : " + str(test_list))

# initializing border
bord = "|"

for sub in test_list:
    temp = bord + " "

    # inner row
    for ele in sub:
        temp = temp + str(ele) + " "

    # adding border
    temp = temp + bord
    print(temp)
```

**输出:**

```py
The original list is : [[4, 5, 6], [1, 4, 5], [6, 9, 1], [0, 3, 1]]
| 4 5 6 |
| 1 4 5 |
| 6 9 1 |
| 0 3 1 |
```

**方法 2:使用*运算符+** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，使用*运算符执行连接内部字符的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Custom Matrix Borders
# Using * operator + loop

# initializing list
test_list = [[4, 5, 6], [1, 4, 5], 
             [6, 9, 1], [0, 3, 1]]

# printing original list
print("The original list is : " + str(test_list))

# initializing border
bord = "|"

for sub in test_list:

    # * operator performs task of joining
    print(bord, *sub, bord)
```

**输出:**

```py
The original list is : [[4, 5, 6], [1, 4, 5], [6, 9, 1], [0, 3, 1]]
| 4 5 6 |
| 1 4 5 |
| 6 9 1 |
| 0 3 1 |
```