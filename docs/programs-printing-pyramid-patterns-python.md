# 用 Python 打印金字塔图案的程序

> 原文:[https://www . geesforgeks . org/programs-printing-金字塔-patterns-python/](https://www.geeksforgeeks.org/programs-printing-pyramid-patterns-python/)

可以使用简单 for 循环在 python 中打印模式。**第一个外环**用于处理**的行数**，**内嵌套环**用于处理**的列数**。操作打印语句，可以打印不同的数字模式、字母模式或星形模式。
本文展示了一些模式。

*   **简单金字塔图案**

## 蟒蛇 3

```py
# Python 3.x code to demonstrate star pattern

# Function to demonstrate printing pattern
def pypart(n):

    # outer loop to handle number of rows
    # n in this case
    for i in range(0, n):

        # inner loop to handle number of columns
        # values changing acc. to outer loop
        for j in range(0, i+1):

            # printing stars
            print("* ",end="")

        # ending line after each row
        print("\r")

# Driver Code
n = 5
pypart(n)
```

**Output**

```py
* 
* * 
* * * 
* * * * 
* * * * * 
```

*   **另一种方法:**
    在 Python 3 中使用 List，这可以用一种更简单的方法来完成

## 计算机编程语言

```py
# Python 3.x code to demonstrate star pattern

# Function to demonstrate printing pattern
def pypart(n):
    myList = []
    for i in range(1,n+1):
        myList.append("*"*i)
    print("\n".join(myList))

# Driver Code
n = 5
pypart(n)
```

**Output**

```py
*
**
***
****
*****
```