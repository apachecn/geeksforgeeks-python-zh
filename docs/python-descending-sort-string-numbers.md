# Python–降序排序字符串编号

> 原文:[https://www . geesforgeks . org/python-降序-排序-字符串-数字/](https://www.geeksforgeeks.org/python-descending-sort-string-numbers/)

对列表进行反向排序是一项简单的任务，已经在许多情况下进行了处理。随着机器学习和数据科学的出现，有时我们可以以数字列表的形式获得数据，但以字符串作为数据类型。在这种情况下，泛型排序函数会给出错误的结果，因此必须采用其他几种方法来执行这些特定的任务。让我们讨论一下这是如何实现的。

**方法#1:天真方法**
在天真方法中需要将列表中的所有元素类型转换为整数通过循环迭代。之后，使用通用排序函数来执行任务。降序排序是通过反向传递来完成的。

```py
# Python3 code to demonstrate 
# Descending Sort String Numbers
# using naive method 

# initializing list 
test_list = [ '4', '6', '7', '2', '1']

# printing original list 
print ("The original list is : " + str(test_list))

# Descending Sort String Numbers
# numeric string sorting
for i in range(0, len(test_list)) :
    test_list[i] = int(test_list[i])
test_list.sort(reverse = True)

# printing result
print ("The resultant reverse sorted list : " + str(test_list))
```

**Output :**

```py
The original list is : ['4', '6', '7', '2', '1']
The resultant reverse sorted list : [7, 6, 4, 2, 1]

```