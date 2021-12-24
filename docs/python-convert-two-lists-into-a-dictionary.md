# Python |将两个列表转换成字典

> 原文:[https://www . geesforgeks . org/python-convert-two-list-in-a-dictionary/](https://www.geeksforgeeks.org/python-convert-two-lists-into-a-dictionary/)

在实时应用中，数据类型之间的相互转换通常是必要的，因为某些系统有某些模块需要特定数据类型的输入。让我们讨论一个简单而有用的工具，将两个列表转换成一个`key:value`对字典。

**方法#1 :** 天真法
可以应用于执行此任务的基本方法是实现此目的的蛮力法。为此，只需声明一个字典，然后对这两个列表运行嵌套循环，并将键和值对从列表值分配给字典。

```py
# Python3 code to demonstrate 
# conversion of lists to dictionary
# using naive method

# initializing lists
test_keys = ["Rash", "Kil", "Varsha"]
test_values = [1, 4, 5]

# Printing original keys-value lists
print ("Original key list is : " + str(test_keys))
print ("Original value list is : " + str(test_values))

# using naive method
# to convert lists to dictionary
res = {}
for key in test_keys:
    for value in test_values:
        res[key] = value
        test_values.remove(value)
        break  

# Printing resultant dictionary 
print ("Resultant dictionary is : " +  str(res))
```

**Output:**

```py
Original key list is : ['Rash', 'Kil', 'Varsha']
Original value list is : [1, 4, 5]
Resultant dictionary is : {'Varsha': 5, 'Rash': 1, 'Kil': 4}

```