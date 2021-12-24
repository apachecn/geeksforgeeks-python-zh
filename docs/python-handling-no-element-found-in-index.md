# Python |处理在索引()中找不到元素

> 原文:[https://www . geesforgeks . org/python-handling-no-element-find-in-index/](https://www.geeksforgeeks.org/python-handling-no-element-found-in-index/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要检查列表中是否存在某个元素，以及它出现的确切位置和索引。方便的解决方法是使用`index()`。但是这可能会带来问题，有时，列表中可能没有所需的元素。让我们讨论一个可以处理这个异常的方法。

**方法:使用`ValueError + try + except`**

在这个方法中，知道值可能不存在，我们在 try-except 块中捕获错误。ValueError 在不存在的情况下引发，可用于捕获此特定异常。

```py
# Python3 code to demonstrate working of
# Handling no element found in index()
# Using try + except + ValueError

# initializing list
test_list = [6, 4, 8, 9, 10]

# printing list
print("The original list : " + str(test_list))

# Handling no element found in index()
# Using try + except + ValueError
try :
    test_list.index(11)
    res = "Element found"
except ValueError :
    res = "Element not in list !"

# Printing result
print("The value after catching error : " + str(res))
```

**输出:**

```py

The original list : [6, 4, 8, 9, 10]
The value after catching error : Element not in list!

```