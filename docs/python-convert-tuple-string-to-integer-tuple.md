# Python–将元组字符串转换为整数元组

> 原文:[https://www . geesforgeks . org/python-convert-tuple-string-to-integer-tuple/](https://www.geeksforgeeks.org/python-convert-tuple-string-to-integer-tuple/)

数据的相互转换是开发人员通常要处理的一个常见问题。将元组字符串转换为整数元组可能会面临一个问题。让我们讨论执行这项任务的某些方法。

**方法#1:使用`tuple() + int() + replace() + split()`**
以上方法的组合可以用来执行此任务。在本例中，我们使用 tuple()和 int()执行转换。元素的提取是通过 replace()和 split()完成的。

```py
# Python3 code to demonstrate working of 
# Convert Tuple String to Integer Tuple
# Using tuple() + int() + replace() + split()

# initializing string 
test_str = "(7, 8, 9)" 

# printing original string 
print("The original string is : " + test_str)

# Convert Tuple String to Integer Tuple
# Using tuple() + int() + replace() + split()
res = tuple(int(num) for num in test_str.replace('(', '').replace(')', '').replace('...', '').split(', '))

# printing result 
print("The tuple after conversion is : " + str(res)) 
```

**Output :**

```py
The original string is : (7, 8, 9)
The tuple after conversion is : (7, 8, 9)

```