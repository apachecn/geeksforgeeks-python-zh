# Python |用参数初始化元组

> 原文:[https://www . geesforgeks . org/python-initialize-元组-with-parameters/](https://www.geeksforgeeks.org/python-initialize-tuples-with-parameters/)

本文讨论用参数初始化元组。即默认值、大小和特定索引处的特定值。让我们讨论执行这项任务的某些方法。

**方法#1:使用`tuple()` + `*`操作符**
可以使用上述功能的组合来执行该任务。在这里，我们使用*运算符扩展默认值，并使用`tuple()`执行元组的形成

```
# Python3 code to demonstrate working of
# Initialize tuples with parameters
# Using tuple() + * operator

# Initializing size 
N = 6

# Initializing default value 
def_val = 2

# Initializing index to add value 
idx = 3 

# Initializing value to be added 
val = 9

# Initialize tuples with parameters
# Using tuple() + * operator
res = [def_val] * N
res[idx] = val 
res = tuple(res)

# printing result
print("The formulated tuple is : " + str(res))
```

**Output :**

```
The formulated tuple is : (2, 2, 2, 9, 2, 2)

```