# Python–将蛇皮箱字符串转换为驼皮箱

> 原文:[https://www . geesforgeks . org/python-convert-snake-case-string-to-camel-case/](https://www.geeksforgeeks.org/python-convert-snake-case-string-to-camel-case/)

给定一个蛇格字符串，转换为骆驼格。

> **输入**:test _ str = ' geeksforgeeks _ is _ best _ for _ geeks '
> **输出**:geeksforgeekssissbestferkeks
> **解释**:字符串转换为驼色大小写。
> 
> **输入**:test _ str = ' geeksforgeeks _ best _ for _ geeks '
> **输出**:geeksforgeeks stforgeks
> **解释**:字符串转换为驼色格。

**方法#1:使用 split() + join() + title() +生成器表达式**

上述功能的组合可以用来解决这个问题。在这种情况下，我们首先拆分所有下划线，然后使用生成器表达式和 title()连接附加了初始单词的字符串，然后是标题大小写的单词。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert Snake Case String to Camel Case
# Using split() + join() + title() + generator expression

# initializing string
test_str = 'geeksforgeeks_is_best'

# printing original string
print("The original string is : " + str(test_str))

# split underscore using split
temp = test_str.split('_')

# joining result 
res = temp[0] + ''.join(ele.title() for ele in temp[1:])

# printing result 
print("The camel case string is : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks_is_best
The camel case string is : geeksforgeeksIsBest

```

**方法 2:使用 split()+join()+title()+map()**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 map()执行将逻辑扩展到整个字符串的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert Snake Case String to Camel Case
# Using split() + join() + title() + map()

# initializing string
test_str = 'geeksforgeeks_is_best'

# printing original string
print("The original string is : " + str(test_str))

# saving first and rest using split()
init, *temp = test_str.split('_')

# using map() to get all words other than 1st
# and titlecasing them
res = ''.join([init.lower(), *map(str.title, temp)])

# printing result 
print("The camel case string is : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks_is_best
The camel case string is : geeksforgeeksIsBest

```