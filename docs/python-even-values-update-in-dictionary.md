# Python |字典中偶数值更新

> 原文:[https://www . geesforgeks . org/python-偶数值-字典更新/](https://www.geeksforgeeks.org/python-even-values-update-in-dictionary/)

有时，在使用字典时，我们可能会遇到这样一个问题，即我们需要对偶数键值执行特定的操作。这类问题可能发生在 web 开发领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行这个任务的天真方法。在这种情况下，我们只需运行一个循环来遍历每个键，甚至在字典中进行检查，并执行所需的操作。

```py
# Python3 code to demonstrate working of
# Even values update in dictionary
# Using loop

# Initialize dictionary
test_dict = {'gfg' : 6, 'is' : 4, 'best' : 7}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Using loop
# Even values update in dictionary
for key in test_dict: 
    if test_dict[key] % 2 == 0:
        test_dict[key] *= 3

# printing result 
print("The dictionary after triple even key's value : " + str(test_dict))
```

**Output :**

```py
The original dictionary : {'best': 7, 'is': 4, 'gfg': 6}
The dictionary after triple even key's value : {'best': 7, 'is': 12, 'gfg': 18}

```