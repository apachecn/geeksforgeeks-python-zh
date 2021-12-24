# Python |获取大于 K 的第一个元素的索引

> 原文:[https://www . geesforgeks . org/python-get-第一个元素的索引-大于-k/](https://www.geeksforgeeks.org/python-get-the-index-of-first-element-greater-than-k/)

Python 列表操作总是需要人手不足，因为它们在开发中的许多地方都有使用。因此，了解它们总是非常有用的。
让我们来寻找一个这样的效用，第一个元素的指数大于 K 的一个线性。有多种方法可以实现这一点。

**方法#1:使用`next() + enumerate()`**
使用`next()`将迭代器返回到已经使用了`enumerate()`的元素。我们简单地把枚举的条件和`next()`挑选合适的元素索引。

```
# Python3 code to demonstrate 
# to find index of first element just 
# greater than K 
# using enumerate() + next()

# initializing list
test_list = [0.4, 0.5, 11.2, 8.4, 10.4]

# printing original list
print ("The original list is : " + str(test_list))

# using enumerate() + next() to find index of
# first element just greater than 0.6 
res = next(x for x, val in enumerate(test_list)
                                  if val > 0.6)

# printing result
print ("The index of element just greater than 0.6 : "
                                           + str(res))
```

**Output:**

```
The original list is : [0.4, 0.5, 11.2, 8.4, 10.4]
The index of element just greater than 0.6 : 2

```