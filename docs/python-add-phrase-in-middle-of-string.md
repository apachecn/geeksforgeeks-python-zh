# Python–在字符串中间添加短语

> 原文:[https://www . geesforgeks . org/python-字符串中间添加短语/](https://www.geeksforgeeks.org/python-add-phrase-in-middle-of-string/)

给定一个字符串，在其中添加一个短语。

> **输入** : test_str = 'geekforgeeks 是给极客用的'，mid _ str = ' good "
> **输出** : geekforgeeks 是给极客用的
> **解释**:刚好加在中间，后面 2 个字。
> 
> **输入**:test _ str = ' geek forgek best '，mid _ str = ' is "
> **输出**:geek forgek best
> **解释**:刚好加在中间，后加 1 个字。

**方法#1:使用** [**分割()**](https://www.geeksforgeeks.org/python-string-split/) **+** [**切片**](https://www.geeksforgeeks.org/string-slicing-in-python/) **+** [**连接()**](https://www.geeksforgeeks.org/join-function-python/)

在这种情况下，字符串被转换成一个单词列表，然后中间的位置被提取出来附加一个新的短语。添加之后，使用 join()对字符串进行反向转换。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Add Phrase in middle of String
# Using split() + slicing + join()

# initializing string
test_str = 'geekforgeeks is for geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing mid string
mid_str = "best"

# splitting string to list
temp = test_str.split()
mid_pos = len(temp) // 2

# appending in mid
res = temp[:mid_pos] + [mid_str] + temp[mid_pos:]

# conversion back
res = ' '.join(res)

# printing result
print("Formulated String : " + str(res))
```

**Output**

```py
The original string is : geekforgeeks is for geeks
Formulated String : geekforgeeks is best for geeks

```

**方法 2:使用 split() + slicing + join()【更紧凑】**

类似于上面的方法，只是用单线的方式来解决这个问题，争取更紧凑。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Add Phrase in middle of String
# Using split() + slicing + join()

# initializing string
test_str = 'geekforgeeks is for geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing mid string
mid_str = "best"

# splitting string to list
temp = test_str.split()
mid_pos = len(temp) // 2

# joining and construction using single line
res = ' '.join(temp[:mid_pos] + [mid_str] + temp[mid_pos:])

# printing result
print("Formulated String : " + str(res))
```

**Output**

```py
The original string is : geekforgeeks is for geeks
Formulated String : geekforgeeks is best for geeks

```