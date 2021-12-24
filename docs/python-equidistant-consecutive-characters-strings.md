# Python–等距连续字符串

> 原文:[https://www . geesforgeks . org/python-等距-连续-字符-字符串/](https://www.geeksforgeeks.org/python-equidistant-consecutive-characters-strings/)

给定一个字符串列表，提取所有字符串，这些字符串的连续字符在 ASCII 顺序上是相同的。

> **输入**:test _ list =[“ABCD”、“egil”、“mpsv”、“Abd”]
> **输出**:[‘ABCD’，‘mpsv’]
> **解释**:在 mpsv 中，连续的字符都在距离 3 处。
> 
> **输入**:test _ list =[“abcd”、“egil”、“mpsw”、“Abd”]
> **输出**:[‘ABCD’]
> **说明:**在 ABCD 中，连续字符距离为 1。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**全部()**](https://www.geeksforgeeks.org/any-all-in-python/)

在这种情况下，我们使用 all()检查每个字符是否有共同的区别，并使用列表理解来迭代字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Equidistant consecutive characters Strings
# Using list comprehension + all()

# initializing list
test_list = ["abcd", "egil", "mpsv", "abd"]

# printing original list
print("The original list is : " + str(test_list))

# ord() used to get ASCII value
res = [sub for sub in test_list if all(ord(
    sub[idx + 1]) - ord(sub[idx]) == ord(sub[1]) - ord(sub[0]) for idx in range(0, len(sub) - 1))]

# printing result
print("Filtered Strings : " + str(res))
```

**Output**

```
The original list is : ['abcd', 'egil', 'mpsv', 'abd']
Filtered Strings : ['abcd', 'mpsv']

```

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**lambda**](https://www.geeksforgeeks.org/python-lambda/)**+**[**order()**](https://www.geeksforgeeks.org/ord-function-python/)**+all()**

在本文中，我们使用 filter()和 lambda 函数执行过滤任务。order()的任务是获取每个字符的 ASCII 等价物。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Equidistant consecutive characters Strings
# Using list comprehension + all()

# initializing list
test_list = ["abcd", "egil", "mpsv", "abd"]

# printing original list
print("The original list is : " + str(test_list))

# ord() used to get ASCII value 
res = [sub for sub in test_list if all(ord(sub[idx + 1]) - ord(sub[idx]) == ord(sub[1]) - ord(sub[0]) for idx in range(0, len(sub) -1 ))]

# printing result 
print("Filtered Strings : " + str(res))
```

**Output**

```
The original list is : ['abcd', 'egil', 'mpsv', 'abd']
Filtered Strings : ['abcd', 'mpsv']

```