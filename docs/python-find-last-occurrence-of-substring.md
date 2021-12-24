# Python |查找子串

的最后一次出现

> 原文:[https://www . geesforgeks . org/python-find-最后出现的子字符串/](https://www.geeksforgeeks.org/python-find-last-occurrence-of-substring/)

有时，在处理字符串时，我们需要查找字符串中是否存在子字符串。这个问题很常见，它的解决方法以前已经讨论过很多次了。这里讨论获取字符串最后一次出现的变化。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`rindex()`**

如果子字符串出现在字符串中，此方法返回最后一次出现的子字符串。这个函数的缺点是，如果字符串中没有子字符串，它会抛出异常，从而中断代码。

```py
# Python3 code to demonstrate
# Find last occurrence of substring
# using rindex()

# initializing string 
test_string = "GfG is best for CS and also best for Learning"

# initializing target word 
tar_word = "best"

# printing original string 
print("The original string : " + str(test_string))

# using rindex()
# Find last occurrence of substring
res = test_string.rindex(tar_word)

# print result
print("Index of last occurrence of substring is : " + str(res))
```

**Output :**

```py
The original string : GfG is best for CS and also best for Learning
Index of last occurrence of substring is : 28

```

**方法 2:使用`rfind()`**

这是执行此任务的替代方法。这个函数比上面的方法更好的优点是，如果没有找到子字符串，这个函数返回“-1”，而不是抛出错误。

```py
# Python3 code to demonstrate
# Find last occurrence of substring
# using rfind()

# initializing string 
test_string = "GfG is best for CS and also best for Learning"

# initializing target word 
tar_word = "best"

# printing original string 
print("The original string : " + str(test_string))

# using rfind()
# Find last occurrence of substring
res = test_string.rfind(tar_word)

# print result
print("Index of last occurrence of substring is : " + str(res))
```

**Output :**

```py
The original string : GfG is best for CS and also best for Learning
Index of last occurrence of substring is : 28

```