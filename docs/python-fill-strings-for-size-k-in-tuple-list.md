# Python–填充元组列表中大小为 K 的字符串

> 原文:[https://www . geesforgeks . org/python-fill-strings-for-size-k-in-tuple-list/](https://www.geeksforgeeks.org/python-fill-strings-for-size-k-in-tuple-list/)

有时，在使用元组列表时，我们会遇到一个问题，即我们需要执行字符串填充来完成列表中的特定大小。这种类型的询问可能发生在数据域和数据预处理中。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [('Gfg '，' is ')，(' best '，' for ')，(' CS '，' Geeks')]，K = 6，fill _ char = ' # '
> ' T3】输出 : [('Gfg### '，' is#### ')，(' best## '，' for # # # # ')，(' CS### '，' Geeks# ')
> 
> **输入** : test_list = [('Gfg '，' is ')，(' best '，' for ')，(' CS '，' Geeks')]，K = 5，fill_char = '！'
> **输出** : [('Gfg！!'，‘是！！!')，(“最好！”，‘为！!')，(' CS！！!'，‘极客’)]

**方法#1:使用列表理解+ `len()`**
这个功能是可以应用于解决这个问题的蛮力方法的简写。在本例中，我们使用 len()执行检查 K 大小的任务，并通过字符执行所需的填充。

```py
# Python3 code to demonstrate working of 
# Fill Strings for size K in Tuple List
# Using list comprehension + len()

# initializing list
test_list = [('Gfg', 'is'), ('best', 'for'), ('CS', 'Geeks')]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 8

# initializing fill_char
fill_char = '*'

# Fill Strings for size K in Tuple List
# Using list comprehension + len()
res = [(a + fill_char * (K - len(a)), b + fill_char * (K - len(b))) for a, b in test_list]

# printing result 
print("The modified list : " + str(res)) 
```

**Output :**

```py
The original list is : [('Gfg', 'is'), ('best', 'for'), ('CS', 'Geeks')]
The modified list : [('Gfg*****', 'is******'), ('best****', 'for*****'), ('CS******', 'Geeks***')]

```

**方法 2:使用列表理解+ `ljust()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 ljust()执行填充尾随字符的任务。

```py
# Python3 code to demonstrate working of 
# Fill Strings for size K in Tuple List
# Using list comprehension + ljust()

# initializing list
test_list = [('Gfg', 'is'), ('best', 'for'), ('CS', 'Geeks')]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 8

# initializing fill_char
fill_char = '*'

# Fill Strings for size K in Tuple List
# Using list comprehension + ljust()
res = [(a.ljust(K, fill_char), b.ljust(K, fill_char)) for a, b in test_list]

# printing result 
print("The modified list : " + str(res)) 
```

**Output :**

```py
The original list is : [('Gfg', 'is'), ('best', 'for'), ('CS', 'Geeks')]
The modified list : [('Gfg*****', 'is******'), ('best****', 'for*****'), ('CS******', 'Geeks***')]

```