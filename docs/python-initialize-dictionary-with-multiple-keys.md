# Python |多键初始化字典

> 原文:[https://www . geesforgeks . org/python-initialize-dictionary-with-multiple-key/](https://www.geeksforgeeks.org/python-initialize-dictionary-with-multiple-keys/)

有时，在使用字典时，我们可能会遇到一个问题，即需要用多个具有相同值的键来初始化字典。这个应用程序需求可能在 web 开发领域，我们可能希望在这个领域同时声明和初始化。让我们讨论执行这项任务的某些方法。

**方法#1:使用`loop`**
我们可以有一个执行这个特定任务的循环。但这只是部分解决了我们的多重加法问题，但字典必须事先声明。

```py
# Python3 code to demonstrate working of
# Initialize dictionary with multiple keys
# Using loop

# declare dictionary
test_dict = {}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Initialize keys 
test_keys = ['gfg', 'is', 'best']

# Using loop
# Initialize dictionary with multiple keys
for keys in test_keys:
    test_dict[keys] = 4

# printing result 
print("Dictionary after updating multiple key-value : " + str(test_dict))
```

**Output :**

> 原始字典:{}
> 更新多个键值后的字典:{“is”:4，“gfg”:4，“best”:4 }