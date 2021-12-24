# Python–将字符串组合成矩阵

> 原文:[https://www . geesforgeks . org/python-组合-字符串-矩阵/](https://www.geeksforgeeks.org/python-combine-strings-to-matrix/)

有时在处理数据时，我们可以接收字符串形式的单独数据，我们需要将它们编译成 Matrix 以供进一步使用。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `split() + zip()`**
以上功能的组合可以用来执行这个任务。在本文中，我们使用 zip()将字符串组合成 Matrix 行元素，split 执行从字符串中提取单词的任务。

```py
# Python3 code to demonstrate working of 
# Combine Strings to Matrix
# Using list comprehension + zip() + split()

# initializing strings
test_str1 = "Gfg is best"
test_str2 = "1 2 3"

# printing original strings
print("The original string 1 is : " + test_str1)
print("The original string 2 is : " + test_str2)

# Combine Strings to Matrix
# Using list comprehension + zip() + split()
res = [[idx, int(j)] for idx, j in zip(test_str1.split(' '), test_str2.split(' '))]

# printing result 
print("Does Matrix after construction : " + str(res)) 
```

**Output :**

> 原列表 1 为:['Gfg '，' is '，' best']
> 原列表 2 为:[['Gfg '，1]，['is '，2]，['best '，1]，['Gfg '，4]，['is '，8]，['Gfg '，7]]
> 分组后的字典:{'is': [2，8]，' Gfg': [1，4，7]，' best': [1]}