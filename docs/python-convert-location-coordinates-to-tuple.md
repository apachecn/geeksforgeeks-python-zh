# Python |将位置坐标转换为元组

> 原文:[https://www . geesforgeks . org/python-convert-location-coordinates-to-tuple/](https://www.geeksforgeeks.org/python-convert-location-coordinates-to-tuple/)

有时，在处理位置时，我们需要大量的数据，这些数据具有纬度和经度形式的位置点。这些可以是字符串的形式，我们希望得到相同的元组版本。让我们讨论执行这项任务的某些方法。

**方法#1:使用`tuple() + float() + split() + map()`**

上述功能的组合可用于执行该任务。在这种情况下，我们首先将坐标的两个部分分割成一个列表，使用`float()`和`map()`对每个部分应用浮点函数，最后使用`tuple()`将其转换为元组。

```
# Python3 code to demonstrate working of
# Convert location coordinates to tuple
# Using tuple() + float() + split() + map()

# Initializing string
test_str = "44.6463, -49.583"

# printing original string
print("The original string is : " + str(test_str))

# Convert location coordinates to tuple
# Using tuple() + float() + split() + map()
res = tuple(map(float, test_str.split(', ')))

# printing result
print("The coordinates after conversion to tuple are : " + str(res))
```

**Output :**

```
The original string is : 44.6463, -49.583
The coordinates after conversion to tuple are : (44.6463, -49.583)

```

**方法 2:使用`eval()`**
这是执行这一特定任务的单线推荐方法。在这种情况下，`eval()`在内部检测字符串，并转换为以元组元素分隔的浮点数。

```
# Python3 code to demonstrate working of
# Convert location coordinates to tuple
# Using eval()

# Initializing string
test_str = "44.6463, -49.583"

# printing original string
print("The original string is : " + str(test_str))

# Convert location coordinates to tuple
# Using eval()
res = eval(test_str)

# printing result
print("The coordinates after conversion to tuple are : " + str(res))
```

**Output :**

```
The original string is : 44.6463, -49.583
The coordinates after conversion to tuple are : (44.6463, -49.583)

```