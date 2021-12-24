# Python–为初始化的字典键赋值

> 原文:[https://www . geesforgeks . org/python-赋值-初始化-字典-键/](https://www.geeksforgeeks.org/python-assign-values-to-initialized-dictionary-keys/)

有时，在使用 python 字典时，我们可能会遇到一个问题，即需要用值初始化字典键。我们保存一个要初始化的密钥网格。这通常发生在处理 JSON 数据的 web 开发过程中。让我们讨论执行这项任务的某些方法。

**方法#1:使用`dict() + zip()`**
以上方法的组合可以用来执行此任务。在这种情况下，我们将列表值分配给已经构建的网格，zip()有助于根据列表索引映射值。

```
# Python3 code to demonstrate working of 
# Assign values to initialized dictionary keys
# using dict() + zip()

# initializing dictionary 
test_dict = {'gfg' : '', 'is' : '', 'best' : ''} 

# Initializing list 
test_list = ['A', 'B', 'C']

# printing original dictionary 
print("The original dictionary is : " + str(test_dict)) 

# Assign values to initialized dictionary keys
# using dict() + zip()
res = dict(zip(test_dict, test_list))

# printing result  
print("The assigned value dictionary is : " + str(res)) 
```

**Output :**

```
The original dictionary is : {'is': '', 'best': '', 'gfg': ''}
The assigned value dictionary is : {'gfg': 'C', 'best': 'B', 'is': 'A'}

```