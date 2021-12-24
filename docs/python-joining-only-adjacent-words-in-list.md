# Python |仅连接列表中的相邻单词

> 原文:[https://www . geesforgeks . org/python-仅加入相邻单词列表/](https://www.geeksforgeeks.org/python-joining-only-adjacent-words-in-list/)

有时，Python 列表中可能会出现多种类型的数据，有时它会被不希望地标记化，因此我们需要将标记化的单词连接起来，并保持数字不变。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用列表理解+ `"*" operator`**
这个任务可以使用列表理解来执行，首先连接单词，然后连接数字，然后只分离数字，同时连接形成结果字符串。

```
# Python3 code to demonstrate
# joining only adjacent words in list 
# list comprehension + "*" operator

# initializing list  
test_list = ['Geeks', '5', 'for', '9', 'Geeks' , '2', '5']

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + "*" operator
# joining only adjacent words in list
res = [''.join([i for i in test_list if not i.isdigit()]),
                  *[j for j in test_list if j.isdigit()]]

# print result
print("The joined adjacent word list(ignoring digits) : " + str(res))
```

**Output:**

> 原始列表:['Geeks '，' 5 '，' for '，' 9 '，' Geeks '，' 2 '，' 5']
> 连接的相邻单词列表(忽略数字):['GeeksforGeeks '，' 5 '，' 9 '，' 2 '，' 5']