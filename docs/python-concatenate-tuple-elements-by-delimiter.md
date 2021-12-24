# Python–通过分隔符

连接元组元素

> 原文:[https://www . geesforgeks . org/python-concatenate-tuple-按分隔符排列元素/](https://www.geeksforgeeks.org/python-concatenate-tuple-elements-by-delimiter/)

给定一个元组，用分隔符连接元组的每个元素。

> **输入**:test _ tup =(“Gfg”、“is”、4、“Best”)、delim =“”
> **输出** : Gfg、is、4、Best
> **解释**:以“、”连接的元素。
> 
> **输入**:test _ tup =(“Gfg”，“is”，4)，delim = "，"
> **输出** : Gfg，is，4
> **解释**:以“，”连接的元素。

**方法一:使用列表理解**

在本文中，我们使用列表理解中的循环对元组中的每个元素进行迭代，并使用+运算符进行连接。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Concatenate Tuple elements by delimiter
# Using list comprehension

# initializing tuple
test_tup = ("Gfg", "is", 4, "Best")

# printing original tuple
print("The original tuple is : " + str(test_tup))

# initializing delim 
delim = "-"

# using str() to convert elements to string 
# join to convert to string
res = ''.join([str(ele) + delim for ele in test_tup])

# striping stray char 
res = res[ : len(res) - len(delim)]

# printing result 
print("Concatenated Tuple : " + str(res)) 
```

**Output**

```py
The original tuple is : ('Gfg', 'is', 4, 'Best')
Concatenated Tuple : Gfg-is-4-Best

```

**方法 2:使用 join() + map()**

在本例中，我们使用 str()将所有字符转换为字符串，并使用 join()将 str()映射到所有元素，然后进行串联。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Concatenate Tuple elements by delimiter
# Using join() + map()

# initializing tuple
test_tup = ("Gfg", "is", 4, "Best")

# printing original tuple
print("The original tuple is : " + str(test_tup))

# initializing delim 
delim = "-"

# for joining, delim is used 
res = delim.join(map(str, test_tup))

# printing result 
print("Concatenated Tuple : " + str(res)) 
```

**Output**

```py
The original tuple is : ('Gfg', 'is', 4, 'Best')
Concatenated Tuple : Gfg-is-4-Best

```