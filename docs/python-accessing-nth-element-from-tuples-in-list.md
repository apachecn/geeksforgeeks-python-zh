# Python |从列表中的元组访问第 n 个元素

> 原文:[https://www . geesforgeks . org/python-access-n-element-from-tuples-in-list/](https://www.geeksforgeeks.org/python-accessing-nth-element-from-tuples-in-list/)

在使用元组时，我们将不同的数据存储为不同的元组元素。有时，需要打印元组中的特定信息。例如，一段代码想要打印所有学生数据的名字。让我们讨论一下如何解决这个问题。

**方法一:使用列表理解**
列表理解是解决这个问题最简单的方法。我们可以只迭代所有索引中的特定索引值，并将其存储在列表中，然后打印出来。

```py
# Python3 code to demonstrate 
# get nth tuple element from list
# using list comprehension 

# initializing list of tuples
test_list = [(1, 'Rash', 21), (2, 'Varsha', 20), (3, 'Kil', 19)]

# printing original list 
print ("The original list is : " + str(test_list))

# using list comprehension to get names
res = [lis[1] for lis in test_list]

# printing result
print ("List with only nth tuple element (i.e names) : " + str(res))
```

**输出:**

```py
The original list is : [(1, 'Rash', 21), (2, 'Varsha', 20), (3, 'Kil', 19)]
List with only nth tuple element (i.e names) : ['Rash', 'Varsha', 'Kil']

```

**方法 2:使用`map() + itemgetter()`**
`map()`再配合`itemgetter()`可以用更简单的方式执行这个任务。 `map()`使用`itemgetter()`映射我们访问的所有元素，并返回结果。

```py
# Python3 code to demonstrate 
# get nth tuple element from list
# using map() + itergetter()
from operator import itemgetter

# initializing list of tuples
test_list = [(1, 'Rash', 21), (2, 'Varsha', 20), (3, 'Kil', 19)]

# printing original list 
print ("The original list is : " + str(test_list))

# using map() + itergetter() to get names
res = list(map(itemgetter(1), test_list))

# printing result
print ("List with only nth tuple element (i.e names) : " + str(res))
```

**输出:**

```py
The original list is : [(1, 'Rash', 21), (2, 'Varsha', 20), (3, 'Kil', 19)]
List with only nth tuple element (i.e names) : ['Rash', 'Varsha', 'Kil']

```

**方法#3:使用`zip()`**
执行这一特定任务的最常规和最精确的方法是使用该功能。这将所有第 n 个元组元素收集到一个容器中，并返回结果。这仅适用于 Python 2。

```py
# Python code to demonstrate 
# get nth tuple element from list
# using zip()

# initializing list of tuples
test_list = [(1, 'Rash', 21), (2, 'Varsha', 20), (3, 'Kil', 19)]

# printing original list 
print ("The original list is : " + str(test_list))

# using zip() to get names
res = list(zip(*test_list)[1])

# printing result
print ("List with only nth tuple element (i.e names) : " + str(res))
```

**输出:**

```py
The original list is : [(1, 'Rash', 21), (2, 'Varsha', 20), (3, 'Kil', 19)]
List with only nth tuple element (i.e names) : ['Rash', 'Varsha', 'Kil']

```