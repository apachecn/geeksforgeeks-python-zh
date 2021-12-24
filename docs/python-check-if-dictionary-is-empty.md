# Python |检查字典是否为空

> 原文:[https://www . geesforgeks . org/python-check-if-dictionary-is-empty/](https://www.geeksforgeeks.org/python-check-if-dictionary-is-empty/)

有时，我们需要检查特定的字典是否为空。这个特殊的任务在 web 开发领域中有它的应用，在这个领域中，我们有时需要测试一个特殊查询的结果，或者检查我们是否有任何键将信息添加到数据库中。让我们讨论执行这项任务的某些方法。

**方法#1:使用`bool()`**

bool 函数可以用来执行这个特殊的任务。顾名思义，它执行将对象转换为布尔值的任务，但是在这里，传递一个空字符串会返回一个 False，因为无法转换空的东西。

```
# Python3 code to demonstrate
# Check if dictionary is empty
# using bool()

# initializing empty dictionary
test_dict = {}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# using bool()
# Check if dictionary is empty 
res = not bool(test_dict)

# print result
print("Is dictionary empty ? : " + str(res))
```

**Output :**

```
The original dictionary : {}
Is dictionary empty ? : True

```

**方法 2:使用`not operator`**

也可以使用 not 运算符来执行此任务，该运算符检查字典是否存在，如果在字典中找不到任何键，则计算结果为 True。

```
# Python3 code to demonstrate
# Check if dictionary is empty
# using not operator

# initializing empty dictionary
test_dict = {}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# using not operator
# Check if dictionary is empty 
res = not test_dict

# print result
print("Is dictionary empty ? : " + str(res))
```

**Output :**

```
The original dictionary : {}
Is dictionary empty ? : True

```