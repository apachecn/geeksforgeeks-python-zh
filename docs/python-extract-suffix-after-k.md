# Python | K 后提取后缀

> 原文:[https://www . geesforgeks . org/python-extract-后缀-after-k/](https://www.geeksforgeeks.org/python-extract-suffix-after-k/)

有时候，我们可能有一个用例，需要在字符串中找到一个后缀。但是有时候，对于获取后缀的决定，需求可能是动态的，比如特定的输入字符，而不是元素的数量。
我们来讨论一下在某个字符后面找到字符串后缀的某些方法。

**方法#1:使用`rsplit()`**
这种方法最初执行的是从后端拆分琴弦的任务，而不是传统的从左到右的方式。不过，为了解决这个特殊问题，这可以限制为 1。

```py
# Python3 code to demonstrate working of
# Extract suffix after K
# Using rsplit()

# initializing string 
test_str = "GeeksforGeeks"

# initializing split character
spl_char = "r"

# printing original string 
print("The original string is : " + str(test_str))

# Using rsplit()
# Extract suffix after K
res = test_str.rsplit(spl_char, 1)[1]

# printing result 
print("The suffix string is : " + str(res))
```

**Output :**

```py
The original string is : GeeksforGeeks
The suffix string is : Geeks

```