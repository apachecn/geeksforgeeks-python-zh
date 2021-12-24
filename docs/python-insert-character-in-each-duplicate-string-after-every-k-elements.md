# Python–在每 K 个元素后的每个重复字符串中插入字符

> 原文:[https://www . geesforgeks . org/python-每 k 个元素后插入一个重复字符字符串/](https://www.geeksforgeeks.org/python-insert-character-in-each-duplicate-string-after-every-k-elements/)

给定一个字符串和一个字符，在每 K 次出现后插入一个字符。

> **输入** : test_str = 'GeeksforGeeks '，K = 2，add _ chr = "；"
> 输出:['；' GeeksforGeeks '，' Ge；“极客”；‘sforGeeks’，Geeksf“极客”；极客’，‘极客’forge；eks '，' GeeksforGeeks']
> **说明**:添加后的所有组合；每 K 个元素之后。
> 
> **输入** : test_str = 'GeeksforGeeks '，K = 2，add _ chr = " *
> **输出** : ['*GeeksforGeeks '，' Ge*eksforGeeks '，' Geeks * forgeeks '，' Geeksfor*Geeks '，' Geeks forge * eks ']
> **解释**:每 K 个元素后加*后的所有组合。

**方法一:使用循环+字符串切片**

这是执行这项任务的方法之一。在这种情况下，我们使用字符串切片对每个 Kth 事件进行字符串切片，并在它们之间添加字符。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Insert character after every K elements
# Using loop + string slicing

# Function to Insert character
# in each duplicate string
# after every K elements
def insertCharacterAfterKelements(test_str, K, char):
    res = []
    # using loop to iterate
    for idx in range(0, len(test_str), K):

        # appending all the results
        res.append(test_str[:idx] + char + test_str[idx:])

    return str(res)

# Driver Code
# initializing string
input_str = 'GeeksforGeeks'

# printing original string
print("The original string is : " + str(input_str))

# initializing K
K = 2

# initializing add char
add_chr = ";"

# printing result
print("The extracted strings : " +
      insertCharacterAfterKelements(input_str, K, add_chr))
```

**输出:**

> 原字符串为:GeeksforGeeks
> 提取的字符串:['；' GeeksforGeeks '，' Ge；“极客”；‘sforGeeks’，Geeksf“极客”；极客’，‘极客’forge；eks '，' GeeksforGeeks']

**方法二:使用列表理解+字符串切片**

这是执行这项任务的另一种方式。在这种情况下，我们执行类似于循环差的任务，即列表理解被用作解决这个问题的简写。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Insert character after every K elements
# Using list comprehension + string slicing

# Function to Insert character
# in each duplicate string
# after every K elements
def insertCharacterAfterKelements(test_str, K, char):
    # list comprehension to bind logic in one.
    res = [test_str[:idx] + char + test_str[idx:]
           for idx in range(0, len(test_str), K)]

    return str(res)

# Driver Code
# initializing string
input_str = 'GeeksforGeeks'

# printing original string
print("The original string is : " + str(input_str))

# initializing K
K = 2

# initializing add char
add_chr = ";"

# printing result
print("The extracted strings : " +
      insertCharacterAfterKelements(input_str, K, add_chr))
```

**输出:**

> 最初的字符串是:GeeksforGeeks
> 提取的字符串:[’；GeeksforGeeks，Ge；eksforGeeks，Geek 投资机会:sforGeeks、GeeksforGeeks，Geeksfor 极客”，“极客”forge；eks '，' GeeksforGeeks’]