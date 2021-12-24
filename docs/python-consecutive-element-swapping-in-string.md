# Python |字符串中的连续元素交换

> 原文:[https://www . geesforgeks . org/python-continuous-element-switching-in-string/](https://www.geeksforgeeks.org/python-consecutive-element-swapping-in-string/)

有时，在处理字符串时，我们可能会遇到一个问题，即我们可能需要执行字符串中连续元素的交换。让我们讨论执行这项任务的某些方法。

**方法#1:使用`join() + zip()` +生成器表达式**
以上功能的组合可以解决这个问题。在本例中，我们使用 zip()执行连接连续字符的任务，生成器表达式用于提供交换逻辑。

```py
# Python3 code to demonstrate working of
# Consecutive element swapping in String
# using join() + zip() + generator expression

# initializing string 
test_str = "gfgisbesty"

# printing original string 
print("The original string is : " + test_str)

# Consecutive element swapping in String
# using join() + zip() + generator expression
res = ''.join([char[1] + char[0] for char in zip(test_str[::2], test_str[1::2])])

# printing result
print("String after Consecutive Swapping : " + str(res))
```

**Output :**

```py
The original string is : gfgisbesty
String after Consecutive Swapping : fgigbsseyt

```