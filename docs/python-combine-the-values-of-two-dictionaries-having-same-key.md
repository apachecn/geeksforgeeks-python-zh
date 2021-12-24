# Python |合并两个关键字相同的字典的值

> 原文:[https://www . geesforgeks . org/python-合并两个字典的值-具有相同的键/](https://www.geeksforgeeks.org/python-combine-the-values-of-two-dictionaries-having-same-key/)

词典是一个无序的、可变的、有索引的集合。在 Python 中，字典是用花括号写的，它们有键和值。它广泛用于日常编程、web 开发和机器学习。词典合并是词典操作中非常常见的任务。

让我们看看如何组合两个具有相同关键字的字典的值。

**方法#1:使用`Counter`**
计数器是字典的一个特殊子类，在大多数情况下执行与字典相同的动作。

```
# Python code to demonstrate combining 
# two dictionaries having same key

from collections import Counter

# initialising dictionaries
ini_dictionary1 = Counter({'nikhil': 1, 'akash' : 5,
                     'manjeet' : 10, 'akshat' : 15})
ini_dictionary2 = Counter({'akash' : 7, 'akshat' : 5,
                                          'm' : 15})

# printing initial dictionaries
print ("initial 1st dictionary", str(ini_dictionary1))
print ("initial 2nd dictionary", str(ini_dictionary2))

# combining dictionaries
# using Counter
final_dictionary = ini_dictionary1 + ini_dictionary2

# printing final result
print ("final dictionary", str(final_dictionary))
```

**Output:**

> 初始第一字典计数器({'akshat': 15，' manjeet': 10，' akash': 5，' nikhil': 1})
> 初始第二字典计数器({'m': 15，' akash': 7，' akshat': 5})
> 最终字典计数器({'akshat': 20，' m': 15，' akash': 12，' manjeet': 10，' nikhil': 1})