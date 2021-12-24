# Python |两个字符串的交集

> 原文:[https://www . geesforgeks . org/python-两个字符串的交集/](https://www.geeksforgeeks.org/python-intersection-of-two-string/)

字符串操作之一可以是计算两个字符串的交集，即输出出现在两个字符串中的公共值。

Python 中有各种各样的方法，通过它们我们可以执行两个字符串的交集。

**方法#1 :** 简单方法
创建一个空字符串，检查两个字符串共有的字符的新出现，并将其追加。因此计算新的交集字符串。这可以通过循环和 if/else 语句来实现。

```
# Python3 code to demonstrate 
# string intersection
# using naive method 

# initializing strings
test_str1 = 'GeeksforGeeks'
test_str2 = 'Codefreaks'

# using naive method to
# get string intersection
res = ""
for i in test_str1:
    if i in test_str2 and not i in res:
        res += i

# printing intersection
print ("String intersection is : " + res)
```

**输出:**

```
String intersection is : eksfor

```

**方法 2 :** 使用`set() + intersection()`

首先使用`set()`将两个字符串转换成集合，然后使用`intersection()`进行交集。返回排序后的集合。

```
# Python3 code to demonstrate 
# string intersection
# using set() + intersection()

# initializing strings
test_str1 = 'GeeksforGeeks'
test_str2 = 'Codefreaks'

# using set() + intersection() to
# get string intersection
res = set(test_str1).intersection(test_str2)

# printing intersection
print ("String intersection is : " + str(res))
```

**输出:**

```
String intersection is : {'e', 'f', 's', 'o', 'k', 'r'}

```

**方法 3 :** 使用`join()`

`join()`在列表的情况下，执行类似于列表理解的任务。这封装了整个交集逻辑，并将通过交集逻辑过滤的每个元素连接到一个字符串中，从而计算交集。它将字符串转换成集合，然后对它们进行计算&运算。

```
# Python3 code to demonstrate 
# string intersection
# using join()

# initializing strings
test_str1 = 'GeeksforGeeks'
test_str2 = 'Codefreaks'

# using join() to
# get string intersection
res = ''.join(sorted(set(test_str1) &
         set(test_str2), key = test_str1.index))

# printing intersection
print ("String intersection is : " + str(res))
```

**输出:**

```
String intersection is : eksfor

```