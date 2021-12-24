# Python |检查列表中的所有值是否都小于给定值

> 原文:[https://www . geesforgeks . org/python-检查列表中的所有值是否小于给定值/](https://www.geeksforgeeks.org/python-check-if-all-the-values-in-a-list-are-less-than-a-given-value/)

给定一个列表，编写一个 Python 程序来检查列表中的所有值是否都小于给定值。

**示例:**

```py
Input : list = [11, 22, 33, 44, 55] 
        value = 22 
Output : No

Input : list = [11, 22, 33, 44, 55] 
        value = 65 
Output : Yes
```

**方法#1:** 遍历列表
通过遍历列表比较每个元素，检查给定列表中的所有元素是否小于给定值。

```py
# Python program to check if all values 
# in the list are less than given value

# Function to check the value
def CheckForLess(list1, val): 

    # traverse in the list 
    for x in list1: 

        # compare with all the  
        # values with value
        if val <= x: 
            return False
    return True

# Driver code 
list1 = [11, 22, 33, 44, 55] 
val = 65
if (CheckForLess(list1, val)): print("Yes")
else: print("No")
```

**输出:**

```py
Yes
```

**方法 2:** 使用`all()`功能
使用`all()`功能，我们可以检查是否所有值都小于单行中的任何给定值。如果 all()函数中的给定条件对所有值都为真，则返回 true，否则返回 false。

```py
# Python program to check if all values 
# in the list are less than given value

# Function to check the value
def CheckForLess(list1, val): 
    return(all(x < val for x in list1)) 

# Driver code 
list1 = [11, 22, 33, 44, 55] 
val = 65
if (CheckForLess(list1, val)): print("Yes")
else: print("No")
```

**输出:**

```py
Yes
```