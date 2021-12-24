# Python–提取字符串，直到其他字符串中出现所有字符

> 原文:[https://www . geeksforgeeks . org/python-extract-string-to-all-出现字符-from-other-string/](https://www.geeksforgeeks.org/python-extract-string-till-all-occurrence-of-characters-from-other-string/)

给定一个字符串，任务是编写一个 Python 程序来提取，直到找到其他字符串中的所有字符。

> **输入:** test_str =“极客 forgeeks 最适合所有极客”，check_str =“怪胎”
> 
> **输出:**极客 forgeeks 最适合 a
> 
> **解释:** a 是 freak 中最后一个以字符串形式出现的字母。字符串会一直打印到第一次出现。
> 
> **输入:** test_str = "geeksforgeeks 最适合所有的极客"，check_str = "geeki "
> 
> **输出:** geeksforgeeks i
> 
> **解释:**我是怪物中最后一个以字符串形式出现的字母。字符串会一直打印到第一次出现 I。

**方法#1:使用**[**all()**](https://www.geeksforgeeks.org/python-all-function/)**+**[**切片**](https://www.geeksforgeeks.org/python-list-slicing/) **+** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，构造子字符串，直到循环中的当前索引，然后从该字符串中，使用 all()检查其他字符串中的所有元素。如果都存在，则返回子字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract String till all occurrence of characters from other string
# Using all() + slicing + loop

# initializing string
test_str = "geeksforgeeks is best for all geeks"

# printing original string
print("The original string is : " + str(test_str))

# initializing check string
check_str = "freak"

for idx in range(1, len(test_str)):
    temp = test_str[:idx]

    # checking for all chars of check_str in substring
    if all([char in temp for char in check_str]):
        res = temp
        break

# printing result
print("String till all characters occurred : " + str(res))
```

**输出:**

```
The original string is : geeksforgeeks is best for all geeks
String till all characters occurred : geeksforgeeks is best for a
```

**方法 2:使用** [**找到()**](https://www.geeksforgeeks.org/python-string-find/)**+**[**max()**](https://www.geeksforgeeks.org/python-max-function/)**+**[**切片**](https://www.geeksforgeeks.org/python-list-slicing/)

在这种情况下，将迭代检查字符串中的每个字符，检查所有字符的索引，并记录最大值。子串被切割，直到最大索引是必需的答案。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract String till all occurrence of characters from other string
# Using find() + max() + slice

# initializing string
test_str = "geeksforgeeks is best for all geeks"

# printing original string
print("The original string is : " + str(test_str))

# initializing check string
check_str = "freak"

# max() find maximum index of all characters
res = test_str[:max([test_str.find(idx) for idx in check_str]) + 1]

# printing result
print("String till all characters occurred : " + str(res))
```

**输出:**

```
The original string is : geeksforgeeks is best for all geeks
String till all characters occurred : geeksforgeeks is best for a
```