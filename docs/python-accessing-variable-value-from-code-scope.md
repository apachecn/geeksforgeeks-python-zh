# Python |从代码范围

访问变量值

> 原文:[https://www . geesforgeks . org/python-access-variable-value-from-code-scope/](https://www.geeksforgeeks.org/python-accessing-variable-value-from-code-scope/)

有时候，我们只需要访问一个变量，而不是通过它的名字来访问。有许多方法可以从代码范围访问变量。默认情况下，这些是创建的字典，它们将变量值作为字典键值对保存。让我们来谈谈其中的一些功能。

**方法#1:使用`locals()`**
这是一个函数，如果在函数中，则存储函数局部范围内的所有变量的值，如果在函数外部，则存储全局范围内的所有变量的值。

```
# Python3 code to demonstrate working of
# Accessing variable value from code scope
# using locals

# initialize variable
test_var = "gfg is best"

# printing original variable
print("The original variable : " + str(test_var))

# Accessing variable value from code scope
# using locals
res = locals()['test_var']

# printing result
print("Variable accessed using dictionary : " + str(res))
```

**Output :**

```
The original variable : gfg is best
Variable accessed using dictionary : gfg is best

```