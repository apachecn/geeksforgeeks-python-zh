# Python |等距元素列表

> 原文:[https://www . geesforgeks . org/python-等距-元素-列表/](https://www.geeksforgeeks.org/python-equidistant-element-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要构建一个列表，其中使用开始、结束和长度参数自动计算范围。这个问题的解决可以有很多应用。让我们讨论一下执行这项任务的方法。

**方法:使用列表理解**
这个任务可以使用列表理解来执行，简写为循环版本的逻辑。在这种情况下，我们只需使用除法运算计算范围，并将其扩展到增加列表形成等距列表。

```
# Python3 code to demonstrate working of
# Equidistant element list
# using list comprehension

# initializing start value 
strt = 5

# initializing end value 
end = 10

# initializing length
length = 8

# Equidistant element list
# using list comprehension
test_list = [strt + x * (end - strt)/length for x in range(length)]

# Printing result
print("The Equidistant list is : " + str(test_list))
```

**Output :**

```

The Equidistant list is : [5.0, 5.625, 6.25, 6.875, 7.5, 8.125, 8.75, 9.375]

```