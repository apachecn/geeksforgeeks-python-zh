# Python–两个字符串元组的连接

> 原文:[https://www . geesforgeks . org/python-两个字符串元组的串联/](https://www.geeksforgeeks.org/python-concatenation-of-two-string-tuples/)

有时，在处理记录时，我们可能会遇到一个问题，即我们可能需要执行元组的字符串连接。这个问题可能发生在日常编程中。让我们讨论执行这项任务的某些方法。

**方法#1:使用`zip()` +生成器表达式**
以上功能的组合可用于执行该任务。在本例中，我们使用生成器表达式执行字符串连接任务，每个元组的映射索引由 zip()完成。

```py
# Python3 code to demonstrate working of 
# Tuple String concatenation
# using zip() + generator expression 

# initialize tuples 
test_tup1 = ("Manjeet", "Nikhil", "Akshat") 
test_tup2 = (" Singh", " Meherwal", " Garg") 

# printing original tuples 
print("The original tuple 1 : " + str(test_tup1)) 
print("The original tuple 2 : " + str(test_tup2)) 

# Tuple String concatenation
# using zip() + generator expression 
res = tuple(ele1 + ele2 for ele1, ele2 in zip(test_tup1, test_tup2)) 

# printing result 
print("The concatenated tuple : " + str(res)) 
```

**Output :**

```py
The original tuple 1 : ('Manjeet', 'Nikhil', 'Akshat')
The original tuple 2 : (' Singh', ' Meherwal', ' Garg')
The concatenated tuple : ('Manjeet Singh', 'Nikhil Meherwal', 'Akshat Garg')

```