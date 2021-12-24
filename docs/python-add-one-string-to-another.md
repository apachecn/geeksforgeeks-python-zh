# Python |将一个字符串添加到另一个字符串中

> 原文:[https://www . geesforgeks . org/python-将一个字符串添加到另一个字符串/](https://www.geeksforgeeks.org/python-add-one-string-to-another/)

两个字符串的连接已经在各种语言中讨论过多次。但是在 Python 中，将一个字符串添加到另一个字符串的任务相当简单。执行这项任务的知识有许多用途。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`+= operator`**

这个操作符可以用来执行这个连接字符串的特殊任务。这比其他语言中使用的传统方法要简单得多，比如使用一个专用函数来执行这个特定的任务。

```
# Python code to demonstrate
# Adding one string to another
# Using += operator

# initializing string 
test_string = "GFG"

# initializing add_string
add_string = " is best"

# printing original string 
print("The original string : " + str(test_string))

# printing original add string 
print("The add string : " + str(add_string))

# Using += operator
# adding one string to another 
test_string += add_string

# print result
print("The concatenated string is : " + test_string)
```

**Output :**

```
The original string : GFG
The add string :  is best
The concatenated string is : GFG is best

```

**方法 2:使用 `join()`**

我们也可以使用 join 函数来执行字符串连接的任务。与上面的方法相比，这个方法的优势在于我们有很多字符串要连接，而不是只有两个。

```
# Python code to demonstrate
# Adding one string to another
# Using join()

# initializing string 
test_string = "GFG"

# initializing add_string
add_string = " is best"

# printing original string 
print("The original string : " + str(test_string))

# printing original add string 
print("The add string : " + str(add_string))

# Using join()
# adding one string to another 
res = "".join((test_string, add_string))

# print result
print("The concatenated string is : " + res)
```

**Output :**

```
The original string : GFG
The add string :  is best
The concatenated string is : GFG is best

```