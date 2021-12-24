# Python–大于 K 的滤镜和双按键

> 原文:[https://www . geesforgeks . org/python-filter-and-double-key-大于-k/](https://www.geeksforgeeks.org/python-filter-and-double-keys-greater-than-k/)

有时，在使用 Python 字典时，我们可以同时执行操作和过滤后提取某些键的任务。这个问题也可以推广到其他值和操作。这在许多领域都有应用，比如日常编程和网络开发。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是解决这个问题的一种方法。在这种情况下，我们采用蛮力的方式只提取过滤后的元素，并在加倍后存储。

```
# Python3 code to demonstrate working of 
# Filter and Double keys greater than K
# Using loop

# initializing dictionary
test_dict = {'Gfg' : 4, 'is' : 2, 'best': 3, 'for' : 6, 'geeks' : 1}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing K
K = 2

# Filter and Double keys greater than K
# Using loop
res = dict()
for key, val in test_dict.items():
    if val > K:
        res[key] = val * 2

# printing result 
print("The filtred dictionary : " + str(res)) 
```

**Output :**

> 原版词典:{'geeks': 1，' for': 6，' Gfg': 4，' is': 2，' best ':3 }
> filtred 词典:{'for': 12，' Gfg': 8，' best': 6}