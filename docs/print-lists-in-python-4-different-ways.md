# 用 Python 打印列表(4 种不同方式)

> 原文:[https://www . geesforgeks . org/print-list-in-python-4-differential-way/](https://www.geeksforgeeks.org/print-lists-in-python-4-different-ways/)

**用 python 打印一个[列表](https://www.geeksforgeeks.org/list-methods-python/)可以通过以下方式完成:**

1.  **使用 [for 循环](https://www.geeksforgeeks.org/loops-in-python/) :** 从 0 遍历到 len(list)并使用 for 循环逐个打印 list 的所有元素，这是标准的做法。

    ## 计算机编程语言

    ```py
    # Python program to print list
    # using for loop
    a = [1, 2, 3, 4, 5]

    # printing the list using loop
    for x in range(len(a)):
        print a[x],
    ```

    输出:

    ```py
    1 2 3 4 5

    ```

2.  **不使用循环:** *符号用于将列表元素打印在一行中，中间留有空格。要打印新行中或由空格分隔的所有元素，请分别使用**sep =“\ n”**或**sep =“”**。

    ## 计算机编程语言

```py
# Python program to print list
# without using loop

a = [1, 2, 3, 4, 5]

# printing the list using * operator separated 
# by space 
print(*a)

# printing the list using * and sep operator
print("printing lists separated by commas")

print(*a, sep = ", ") 

# print in new line
print("printing lists in new line")

print(*a, sep = "\n")
```