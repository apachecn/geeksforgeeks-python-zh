# Python |检查变量是否为字符串

> 原文:[https://www . geesforgeks . org/python-check-if-a-variable-is-string/](https://www.geeksforgeeks.org/python-check-if-a-variable-is-string/)

在处理不同的数据类型时，我们可能会遇到需要测试数据类型性质的时候。本文给出了根据数据类型测试变量的方法。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用`isinstance(x, str)`**

此方法可用于测试任何变量是否是特定的数据类型。通过给出第二个参数“str”，我们可以检查我们传递的变量是否是字符串。

```
# Python3 code to demonstrate
# Check if variable is string 
# using isinstance()

# initializing string 
test_string = "GFG"

# printing original string 
print("The original string : " + str(test_string))

# using isinstance()
# Check if variable is string 
res = isinstance(test_string, str)

# print result
print("Is variable a string ? : " + str(res))
```

**Output :**

```
The original string : GFG
Is variable a string ? : True

```

**方法 2:使用`type()`**

这个任务也可以使用类型函数来实现，在类型函数中，我们只需要传递变量，并将其等同于一个特定的类型。

```
# Python3 code to demonstrate
# Check if variable is string 
# using type()

# initializing string 
test_string = "GFG"

# printing original string 
print("The original string : " + str(test_string))

# using type()
# Check if variable is string 
res = type(test_string) == str

# print result
print("Is variable a string ? : " + str(res))
```

**Output :**

```
The original string : GFG
Is variable a string ? : True

```