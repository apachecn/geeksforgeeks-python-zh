# 在 Python 中创建两个未排序列表的排序合并列表

> 原文:[https://www . geeksforgeeks . org/创建-排序-合并-列表-两个-未排序-列表-在 python 中/](https://www.geeksforgeeks.org/creating-a-sorted-merged-list-of-two-unsorted-lists-in-python/)

我们需要将 Python 中的两个列表合并成一个。最后，我们显示排序列表。

示例:

```
Input : 
list1 = [25, 18, 9, 41, 26, 31]
list2 = [25, 45, 3, 32, 15, 20]
Output :
[3, 9, 15, 18, 20, 25, 25, 26, 31, 32, 41, 45]

Input : 
list1 = ["suraj", "anand", "gaurav", "aman", "kishore"]
list2 = ["rohan", "ram", "mohan", "priya", "komal"]
Output :
['aman', 'anand', 'gaurav', 'kishore', 'komal', 
'mohan', 'priya', 'ram', 'rohan', 'suraj']

```

Python 中的**加号运算符“+”**帮助我们合并两个列表，无论是字符串列表还是整数列表，或者两者的混合。最后，我们使用 **sort()** 函数对列表进行排序。

```
# Python program to merge and sort two list
def Merge(list1, list2):
    final_list = list1 + list2
    final_list.sort()
    return(final_list)

# Driver Code
list1 = [25, 18, 9, 41, 26, 31]
list2 = [25, 45, 3, 32, 15, 20]
print(Merge(list1, list2))
```

输出:

```
[3, 9, 15, 18, 20, 25, 25, 26, 31, 32, 41, 45]

```