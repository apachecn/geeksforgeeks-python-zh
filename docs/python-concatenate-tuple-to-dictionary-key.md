# Python–将元组连接到字典键

> 原文:[https://www . geesforgeks . org/python-concatenate-tuple-to-dictionary-key/](https://www.geeksforgeeks.org/python-concatenate-tuple-to-dictionary-key/)

给定元组，将它们转换为字典，关键字为串联字符串。

> **输入**:test _ list =[((“gfg”、“is”、“best”)、10)、((“gfg”、“for”、“cs”)、15)]
> **输出**:{“gfg 是 best”:10、“gfg for cs”:15 }
> **解释**:元组字符串串接为字符串。
> 
> **输入**:test _ list =[(((“gfg”、“is”、“best”))，10)】
> **输出**:{‘gfg 是 best’:10 }
> **解释**:元组字符串串接为字符串。

**方法#1:使用循环+连接()**

在本文中，我们使用 join()执行字典键的连接任务，并使用循环来呈现所需的字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Concatenate Tuple to Dictionary Key
# Using loop + join()

# initializing list
test_list = [(("gfg", "is", "best"), 10), (("gfg", "good"), 1), (("gfg", "for", "cs"), 15)]

# printing original list
print("The original list is : " + str(test_list))

res = {}
for sub in test_list:

  # joining for making key
  res[" ".join(sub[0])] = sub[1]

# printing result 
print("The computed Dictionary : " + str(res))
```

**Output**

```py
The original list is : [(('gfg', 'is', 'best'), 10), (('gfg', 'good'), 1), (('gfg', 'for', 'cs'), 15)]
The computed Dictionary : {'gfg is best': 10, 'gfg good': 1, 'gfg for cs': 15}

```

**方法二:利用词典理解**

这是上述方法的简写，类似的功能，只是纸上的一行代码，用于紧凑的解决方案。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Concatenate Tuple to Dictionary Key
# Using dictionary comprehension

# initializing list
test_list = [(("gfg", "is", "best"), 10), (("gfg", "good"), 1), (("gfg", "for", "cs"), 15)]

# printing original list
print("The original list is : " + str(test_list))

# one liner to solve problem 
res = {' '.join(key): val for key, val in test_list}

# printing result 
print("The computed Dictionary : " + str(res))
```

**Output**

```py
The original list is : [(('gfg', 'is', 'best'), 10), (('gfg', 'good'), 1), (('gfg', 'for', 'cs'), 15)]
The computed Dictionary : {'gfg is best': 10, 'gfg good': 1, 'gfg for cs': 15}

```