# 给定字符的 Python-K 长度组合

> 原文:[https://www . geesforgeks . org/python-k-length-combinations-from-given-characters/](https://www.geeksforgeeks.org/python-k-length-combinations-from-given-characters/)

给定一个字符串，在一行中生成 K 个长度组合。

> **输入** : test_str = 'gfg '，K = 3
> **输出** : ['ggg '，' ggf '，' ggg '，' gff '，' gfg '，' ggg '，' ggf '，' ggg '，' fgf '，' fgg '，' fff '，' fgg '，' fgf '，' fgg '，' gfg '，' gff '，' gfg '，' ggf '，' ggg']
> **解释**:的所有组合
> 
> **输入** : test_str = 'G4G '，K = 2
> **输出** : ['GG '，' G4 '，' GG '，' 4G '，' 44 '，' 4G '，' GG '，' G4 '，' GG']
> **解释**:提取 K 长度的所有组合。

**方法#1:使用**[**ITER tools . product()**](https://www.geeksforgeeks.org/python-itertools-product/)**+**[**join()**](https://www.geeksforgeeks.org/join-function-python/)**+**[**map()**](https://www.geeksforgeeks.org/python-map-function/)

该任务可以由 product()使用 repeat param 来执行，但返回的结果是单个字符的元组列表。这些都可以使用 join()和 map()进行连接。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# K length Combinations from given characters shorthand
# Using itertools.product() + join() + map()
from itertools import product

# initializing string
test_str = 'gf4g'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 2

# map and join() used to change return data type
res = list(map(''.join, product(test_str, repeat = K)))

# printing result 
print("The generated Combinations : " + str(res)) 
```

**输出:**

> 原字符串为:gf4g
> 生成的组合:['gg '，' gf '，' g4 '，' gg '，' fg '，' ff '，' f4 '，' fg '，' 4g '，' 4f '，' 44 '，' 4g '，' gg '，' gf '，' g4 '，' gg '

**方法 2:使用 itertools.product() +列表理解**

在这种情况下，列表理解用于连接元素的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# K length Combinations from given characters shorthand
# Using itertools.product() + join() + map()
from itertools import product

# initializing string
test_str = 'gfg'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 2

# list comprehension + join() used to change return data type
res = [''.join(ele) for ele in product(test_str, repeat = K)]

# printing result 
print("The generated Combinations : " + str(res))
```

**输出:**

> 原字符串为:gfg
> 生成的组合:['gg '，' gf '，' gg '，' fg '，' ff '，' fg '，' gg '，' gf '，' gg']