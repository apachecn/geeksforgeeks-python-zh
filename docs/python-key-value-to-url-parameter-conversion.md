# Python |键值到网址参数转换

> 原文:[https://www . geesforgeks . org/python-key-value-to-URL-parameter-conversion/](https://www.geeksforgeeks.org/python-key-value-to-url-parameter-conversion/)

很多时候，在 web 开发领域工作时，我们会遇到这样一个问题:我们需要将我们拥有的一些键值对设置为 URL 参数，这些键值对可以是元组的形式，也可以是键值列表的形式。让我们讨论两种情况的解决方案。

**方法一:使用`urllib.urlencode()`(带元组)**
`urlencode`函数是可以执行我们希望实现的任务的根函数。在元组的情况下，我们可以只传递元组，编码器完成字符串的其余转换。仅适用于 Python2。

```py
# Python code to demonstrate working of
# Key-Value to URL Parameter Conversion
# Using urllib.urlencode() ( with tuples )
import urllib

# initializing tuples
test_tuples = (('Gfg', 1), ('is', 2), ('best', 3))

# printing original tuples
print("The original tuples are : " + str(test_tuples))

# Using urllib.urlencode() ( with tuples )
# Key-Value to URL Parameter Conversion
res = urllib.urlencode(test_tuples)

# printing URL string
print("The URL parameter string is : " + str(res))
```

**Output :**

```py
The original tuples are : (('Gfg', 1), ('is', 2), ('best', 3))
The URL parameter string is : Gfg=1&is=2&best=3

```