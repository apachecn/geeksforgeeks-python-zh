# Python |在列表中连接元组元素

> 原文:[https://www . geesforgeks . org/python-join-tuple-elements-in-a-list/](https://www.geeksforgeeks.org/python-join-tuple-elements-in-a-list/)

如今，数据是任何机器学习技术的支柱。数据可以以任何形式出现，有时需要提取出来进行处理。本文讨论了提取列表元组中存在的信息的问题。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`join() + list comprehension`**
连接函数可以将每个元组元素相互连接，列表理解处理遍历元组的任务。

```
# Python3 code to demonstrate 
# joining tuple elements
# using join() + list comprehension

# initializing tuple list 
test_list = [('geeks', 'for', 'geeks'),
             ('computer', 'science', 'portal')]

# printing original list
print ("The original list is : " + str(test_list))

# using join() + list comprehension
# joining tuple elements 
res = [' '.join(tups) for tups in test_list]

# printing result 
print ("The joined data is : " +  str(res))
```

**Output:**

> 最初的名单是:[(‘极客’，‘为极客’，‘极客’，(‘计算机’，‘科学’，‘门户’)]
> 加入的数据是:[‘极客为极客’，‘计算机科学门户’]