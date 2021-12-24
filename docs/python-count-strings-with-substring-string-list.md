# Python–使用子字符串列表对字符串进行计数

> 原文:[https://www . geesforgeks . org/python-count-strings-with-substring-string-list/](https://www.geeksforgeeks.org/python-count-strings-with-substring-string-list/)

python 可以很容易处理的经典问题是，如果一个字符串是另一个字符串的子串，这个问题已经被处理过很多次了。但是有时，人们希望在字符串列表上扩展这个，并找出有多少字符串满足条件，因此需要遍历整个容器并执行通用算法。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ len()**
列表理解是执行任何特定任务的优雅方式，因为从长远来看，它增加了可读性。这项任务可以用简单的方法完成，因此也可以简化为列表理解。len()用于计算列表的长度。

```
# Python code to demonstrate 
# Count Strings with substring String List
# using list comprehension + len()

# initializing list 
test_list = ['GeeksforGeeks', 'Geeky', 'Computers', 'Algorithms']

# printing original list 
print ("The original list is : " + str(test_list))

# initializing substring
subs = 'Geek'

# using list comprehension + len()
# Count Strings with substring String List
res = len([i for i in test_list if subs in i])

# printing result 
print ("All strings count with given substring are : " + str(res))
```

**Output :**

```
The original list is : ['GeeksforGeeks', 'Geeky', 'Computers', 'Algorithms']
All strings count with given substring are : 2

```