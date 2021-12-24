# Python–将字符串转换为每行有 K 个字符的矩阵

> 原文:[https://www . geesforgeks . org/python-convert-string-to-matrix-having-k-characters-per-row/](https://www.geeksforgeeks.org/python-convert-string-to-matrix-having-k-characters-per-row/)

给定一个字符串，将其转换为矩阵，每行有 K 个字符。

> **输入** : test_str = 'GeeksforGeeks 最好'，K = 7
> **输出** : [['G '，' e '，' e '，' K '，' s '，' f '，' o']，['r '，' G '，' e '，' e '，' e '，' s '，' t ']
> **说明:**每个字符分配给矩阵中的 7 个元素行。
> 
> **输入** : test_str = 'GeeksforGeeks '，K = 7
> **输出** : [['G '，' e '，' e '，' K '，' s '，' f '，' o']，['r '，' G '，' e '，' e '，' K '，' s '，']
> **解释**:每个字符分配给矩阵中的 7 个元素行。

**方法一:使用列表理解+切片**

上述功能的组合可以用来解决这个问题。在本文中，我们首先使用切片和列表理解为每行提取单独的字符串。然后使用 *list()* 将每个字符串转换为字符列表。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert String to K characters row Matrix
# Using list comprehension + slicing

# Function to Convert String
# to K characters row Matrix
def convertToMatrix(test_str, K):
    # slicing strings
    temp = [test_str[idx: idx + K] for idx in range(0, len(test_str), K)]

    # conversion to list of characters
    res = [list(ele) for ele in temp]

    # printing result
    print("The converted Matrix : " + str(res))

# Driver Code    
# initializing string
input_str = 'GeeksforGeeks is best'

# printing original string
print("The original string is : " + str(input_str))

# initializing K
K = 7

# calling the function
convertToMatrix(input_str, K)
```

**输出:**

> 原来的字符串是:GeeksforGeeks 最好
> 转换后的矩阵:[['G '，' e '，' e '，' k '，' s '，' f '，' o']，['r '，' G '，' e '，' e '，' k '，' s '，']，['i '，' s '，' b '，' e '，' s '，' t']]

**方法二:使用列表理解+地图()+切片**

这是执行这项任务的另一种方式。在这种情况下，我们以与上述功能类似的方式执行任务，不同之处在于转换为列表是使用 *map()* 而不是列表理解来完成的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert String to K characters row Matrix
# Using list comprehension + map() + slicing

# Function to Convert String
# to K characters row Matrix
def convertToMatrix(test_str, K):
    # slicing strings
    temp = [test_str[idx: idx + K] for idx in range(0, len(test_str), K)]

    # conversion using map
    res = list(map(lambda ele: list(ele), temp))

    # printing result
    print("The converted Matrix : " + str(res))

# Driver Code
# initializing string
input_str = 'GeeksforGeeks is best'

# printing original string
print("The original string is : " + str(input_str))

# initializing K
K = 7

# calling the function
convertToMatrix(input_str, K)
```

**输出:**

> 原来的字符串是:GeeksforGeeks 最好
> 转换后的矩阵:[['G '，' e '，' e '，' k '，' s '，' f '，' o']，['r '，' G '，' e '，' e '，' k '，' s '，']，['i '，' s '，' b '，' e '，' s '，' t']]