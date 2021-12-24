# Python |获取字典中给定值 N 的键数

> 原文:[https://www . geesforgeks . org/python-获取字典中给定值 n 的键数/](https://www.geeksforgeeks.org/python-get-the-number-of-keys-with-given-value-n-in-dictionary/)

在本文中，我们将看到如何在给定的字典中获取具有某个给定值 N 的键的数量。有多种方法可以完成这项任务。让我们借助例子来看看它们。

**简单方法–**

```py
# Python3 code to Get the number of keys
# with given value N in dictionary

# Initialize dictionary 
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3, 'for' : 2, 'CS' : 2} 

# printing original dictionary 
print("The original dictionary : " + str(test_dict)) 

# Initialize value 
N = 2

# Using loop 
# Selective key values in dictionary 
res = 0
for key in test_dict: 
    if test_dict[key] == N: 
        res = res + 1

# printing result 
print("Frequency of N is : " + str(res)) 
```

**输出:**

```py
The original dictionary : {'CS': 2, 'for': 2, 'is': 2, 'gfg': 1, 'best': 3}
Frequency of N is : 3

```

**方法 2:** 使用 sum() +值()

```py
# Python3 code to Get the number of keys
# with given value N in dictionary
# Using sum() + values() 

# Initialize dictionary 
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3, 'for' : 2, 'CS' : 2} 

# printing original dictionary 
print("The original dictionary : " + str(test_dict)) 

# Initialize value 
N = 2

# Using sum() + values() 
# Selective key values in dictionary
res = sum(x == N for x in test_dict.values()) 

# printing result 
print("Frequency of K is : " + str(res)) 
```

**输出:**

```py
The original dictionary : {'is': 2, 'for': 2, 'gfg': 1, 'best': 3, 'CS': 2}
Frequency of K is : 3

```