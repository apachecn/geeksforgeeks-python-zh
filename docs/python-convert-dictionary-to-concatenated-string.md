# Python–将字典转换为串联字符串

> 原文:[https://www . geesforgeks . org/python-convert-dictionary-to-concated-string/](https://www.geeksforgeeks.org/python-convert-dictionary-to-concatenated-string/)

有时，在使用字典时，我们可能会有一个任务，其中我们需要执行将字典转换为字符串的转换，字符串是串联的键值对。这可以在我们需要减少存储空间或需要字符串作为目标数据的领域中得到应用。让我们讨论执行这项任务的某些方法。

### 方法 1:使用空字符串+进行循环

在这个方法中，我们将使用 for 循环遍历字典对象，并继续向空字符串添加键:值对。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert Dictionary to Concatenated String
# Using an empty string + for loop

# initializing dictionary
test_dict = {'gfg': 1, 'is': 2, 'best': 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Create an empty string
res = ' '

# Convert Dictionary to Concatenated String
# Using for loop and empty string
for item in test_dict:
    res += item + str(test_dict[item])

# printing result
print("The dictionary after concatenation is : " + str(res))
```

**输出:**

```
The original dictionary is : {'gfg': 1, 'is': 2, 'best': 3}
The dictionary after concatenation is :  gfg1is2best3
```

### **方法 2:使用 join() + items()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们需要使用 join()执行连接任务，并且使用 items()完成字典项的提取。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert Dictionary to Concatenated String
# Using join() + items()

# initializing dictionary
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Convert Dictionary to Concatenated String
# Using join() + items()
res = ''.join(key + str(val) for key, val in test_dict.items())

# printing result
print("The dictionary after concatenation is : " + str(res))
```

**输出:**

```
The original dictionary is : {'gfg': 1, 'best': 2, 'is': 3}
The dictionary after concatenation is : gfg1best2is3
```

### 
**方法三:使用 reduce() + lambda**

上述功能的组合可用于执行该任务。在本文中，我们使用 reduce()和 lambda 的组合来执行串联任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert Dictionary to Concatenated String
# Using reduce() + lambda
from functools import reduce

# initializing dictionary
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Convert Dictionary to Concatenated String
# Using reduce() + lambda
res = reduce(lambda key, val : key + str(val[0]) + str(val[1]), test_dict.items(), '')

# printing result
print("The dictionary after concatenation is : " + str(res))
```

**输出:**

```
The original dictionary is : {'gfg': 1, 'best': 2, 'is': 3}
The dictionary after concatenation is : gfg1best2is3
```