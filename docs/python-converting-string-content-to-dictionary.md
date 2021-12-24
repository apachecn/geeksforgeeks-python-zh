# Python |将字符串内容转换为字典

> 原文:[https://www . geesforgeks . org/python-converting-string-content-to-dictionary/](https://www.geeksforgeeks.org/python-converting-string-content-to-dictionary/)

有时候，我们被字符串所困扰，我们可能不得不把它的内容转换成字典。该字符串可能具有可以进行键值转换的指定格式。这类问题在机器学习领域相当普遍。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`split()` +字典理解**
以上方法的组合可以用来执行这个特定的任务。这是 2 个过程方法。在第一步中，使用拆分将字符串转换为列表，然后使用字典理解将其转换回字典。

```
# Python3 code to demonstrate working of
# Converting String content to dictionary
# Using dictionary comprehension + split()

# initializing string 
test_str = "Gfg = 1, Good = 2, CS = 3, Portal = 4"

# printing original string 
print("The original string is : " + test_str)

# Using dictionary comprehension + split()
# Converting String content to dictionary
res = {key: int(val) for key, val in (item.split('=')
                   for item in test_str.split(', '))}

# printing result 
print("The newly created dictionary : " + str(res))
```

**Output :**

```
The original string is : Gfg = 1, Good = 2, CS = 3, Portal = 4
The newly created dictionary : {' CS ': 3, 'Gfg ': 1, ' Portal ': 4, ' Good ': 2}

```

**方法 2:使用`eval()`**
这个特殊的问题可以通过使用内置函数`eval`来解决，该函数对字符串进行内部求值，并根据条件将字符串转换为字典。

```
# Python3 code to demonstrate working of
# Converting String content to dictionary
# Using eval()

# initializing string 
test_str = "Gfg = 1, Good = 2, CS = 3, Portal = 4"

# printing original string 
print("The original string is : " + test_str)

# Using eval()
# Converting String content to dictionary
res = eval('dict(% s)' % test_str)

# printing result 
print("The newly created dictionary : " + str(res))
```