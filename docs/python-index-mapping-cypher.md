# Python–索引映射 Cypher

> 原文:[https://www.geeksforgeeks.org/python-index-mapping-cypher/](https://www.geeksforgeeks.org/python-index-mapping-cypher/)

有时，在使用 Python 时，我们可能会在安全或游戏领域遇到问题，其中我们需要创建某些密码，它们可能是不同类型的。这包括索引映射密码，在该密码中，我们传递一个整数字符串，并按此顺序获取元素字符。让我们讨论一下构造它的某些方法。

**方法#1:使用循环**
这是一种蛮力方式，可以用这种方式构建。在这种情况下，我们手动检查每个字符，并将其作为索引号映射到字符串中的值。

```
# Python3 code to demonstrate working of 
# Index Mapping Cypher 
# Using loop

# initializing string
test_str = "geeksforgeeks"

# printing original string
print("The original string is : " + test_str)

# initializing cypher string 
cyp_str = "53410"

# Index Mapping Cypher 
# Using loop
res = ""
temp = [int(idx) for idx in cyp_str]
for ele in temp:
    res += test_str[ele]

# printing result 
print("The deciphered value string : " + str(res)) 
```

**Output :**

```
The original string is : geeksforgeeks
The deciphered value string : fkseg

```