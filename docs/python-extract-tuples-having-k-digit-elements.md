# Python–提取具有 K 位元素的元组

> 原文:[https://www . geesforgeks . org/python-extract-元组-having-k-digit-elements/](https://www.geeksforgeeks.org/python-extract-tuples-having-k-digit-elements/)

给定一个元组列表，提取所有具有 K 位元素的元组。

> **输入** : test_list = [(54，2)，(34，55)，(222，23)，(12，45)，(78)，]，K = 2
> **输出** : [(34，55)，(12，45)，(78)，]
> **解释**:所有元组都有 2 位数字。
> 
> **输入** : test_list = [(54，2)，(34，55)，(222，23)，(12，45)，(782)，]，K = 3
> **输出** : [(782，]
> **解释**:所有元组都有 3 位数的数字。

**方法#1:使用**[**all()**](https://www.geeksforgeeks.org/any-all-in-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们通过转换为字符串并检查其长度来检查每个元素是否为 K 位。all()用于检查所有元素的大小是否相似。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract K digit Elements Tuples
# Using all() + list comprehension

# initializing list
test_list = [(54, 2), (34, 55), (222, 23), (12, 45), (78, )]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

# using len() and str() to check length and 
# perform string conversion
res = [sub for sub in test_list if all(len(str(ele)) == K for ele in sub)]

# printing result
print("The Extracted tuples : " + str(res))
```

**输出:**

> 原列表为:[(54，2)，(34，55)，(222，23)，(12，45)，(78)，]
> 提取的元组:[(34，55)，(12，45)，(78，]

**方法 2:使用 all() + filter() + lambda**

这类似于上面的方法，区别是 filter()和 lambda 用于解决过滤问题。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract K digit Elements Tuples
# Using all() + filter() + lambda

# initializing list
test_list = [(54, 2), (34, 55), (222, 23), (12, 45), (78, )]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

# filter() and lambda used for task of filtering
res = list(filter(lambda sub: all(len(str(ele)) == K for ele in sub), test_list))

# printing result
print("The Extracted tuples : " + str(res))
```

**输出:**

> 原列表为:[(54，2)，(34，55)，(222，23)，(12，45)，(78)，]
> 提取的元组:[(34，55)，(12，45)，(78，]