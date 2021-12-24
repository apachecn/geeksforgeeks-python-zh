# Python |获取随机字典对

> 原文:[https://www . geesforgeks . org/python-get-random-dictionary-pair/](https://www.geeksforgeeks.org/python-get-random-dictionary-pair/)

有时，在使用字典时，我们可能会遇到需要从字典中随机查找一对的情况。这类问题可能出现在彩票等游戏中。让我们讨论执行这项任务的某些方法。

**方法#1:使用 random . choice()+list()+items()**
以上方法的组合可以用来执行这个任务。choice 函数执行随机值选择的任务，list 方法用于将使用 items()访问的对转换为 choice 函数可以工作的列表。警告，如果字典包含许多值，重复将其转换为列表可能会导致性能问题。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Get random dictionary pair in dictionary
# Using random.choice() + list() + items()
import random

# Initialize dictionary
test_dict = {'Gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Get random dictionary pair in dictionary
# Using random.choice() + list() + items()
res = key, val = random.choice(list(test_dict.items()))

# printing result
print("The random pair is : " + str(res))
```

**Output : **

```py
The original dictionary is : {'Gfg': 1, 'best': 3, 'is': 2}
The random pair is : ('is', 2)
```

**方法 2:使用 popitem()**
此功能一般用于从字典中移除一个项目并将其移除。为什么这个函数可以用来执行这个任务的逻辑是，字典中的排序不依赖于项目插入的顺序。但是，需要注意的是，在 Python 的较新版本中，同一组项目的顺序总是相同的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Get random dictionary pair in dictionary
# Using popitem()

# Initialize dictionary
test_dict = {'Gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Get random dictionary pair in dictionary
# Using popitem()
res = test_dict.popitem()

# printing result
print("The random pair is : " + str(res))
```

**Output : **

```py
The original dictionary is : {'Gfg': 1, 'best': 3, 'is': 2}
The random pair is : ('is', 2)
```