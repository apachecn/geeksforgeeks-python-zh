# Python |将元组转换为浮点值

> 原文:[https://www . geesforgeks . org/python-convert-tuple-to-float-value/](https://www.geeksforgeeks.org/python-convert-tuple-to-float-value/)

有时，在使用元组时，我们会遇到一个问题，我们需要将元组转换为浮点数，其中第一个元素代表整数部分，下一个元素代表小数部分。让我们讨论一下实现这一目标的具体方法。

**方法:使用`join() + float() + str()` +生成器表达式**

上述功能的结合可以解决这个问题。在这种情况下，我们首先将元组元素转换为字符串，然后将它们连接起来并转换为所需的整数。

```py
# Python3 code to demonstrate working of
# Convert tuple to float
# using join() + float() + str() + generator expression

# initialize tuple
test_tup = (4, 56)

# printing original tuple 
print("The original tuple : " + str(test_tup))

# Convert tuple to float
# using join() + float() + str() + generator expression
res = float('.'.join(str(ele) for ele in test_tup))

# printing result
print("The float after conversion from tuple is : " + str(res))
```

**输出:**

```py
The original tuple : (4, 56)
The float after conversion from tuple is : 4.56

```