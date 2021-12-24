# Python |每个字典键上的 K 模

> 原文:[https://www . geeksforgeeks . org/python-k-模每字典键/](https://www.geeksforgeeks.org/python-k-modulo-on-each-dictionary-key/)

有时候，在使用字典时，我们可能会遇到一个问题，我们需要对每个键值执行特定的操作，比如对每个键执行 K 模运算。这类问题可能发生在 web 开发领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行这个任务的天真方法。在这种情况下，我们只需运行一个循环来遍历字典中的每个键，并执行所需的 K 模运算。

```py
# Python3 code to demonstrate working of
# K modulo on each Dictionary Key
# Using loop

# Initialize dictionary
test_dict = {'gfg' : 6, 'is' : 4, 'best' : 7}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing K 
K = 4

# Using loop
# K modulo on each Dictionary Key
for key in test_dict: 
    test_dict[key] %= 4

# printing result 
print("The dictionary after mod K each key's value : " + str(test_dict))
```

**Output :**

```py
The original dictionary : {'is': 4, 'best': 7, 'gfg': 6}
The dictionary after mod K each key's value : {'is': 0, 'best': 3, 'gfg': 2}

```