# Python |打印字符串时避免引用

> 原文:[https://www . geesforgeks . org/python-避免在打印字符串时引用/](https://www.geeksforgeeks.org/python-avoiding-quotes-while-printing-strings/)

我们经常遇到小问题，结果却是大问题。在编码时，小任务有时会因为处理不好而变得乏味。其中一个任务是输出格式化，我们要求在打印任何列表元素时省略引号。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`join()`**
我们可以通过使用连接方法来简化这个任务，在该方法中，我们通过传递的分隔符(在本例中是逗号)将列表中的字符串连接在一起，从而解决了这个问题。

```py
# Python3 code to demonstrate  
# avoiding printing last comma
# using join()

# initializing list
test_list = ['Geeks', 'For', 'Geeks']

# printing original list 
print ("The original list is : " + str(test_list))

# using join()
# avoiding printing last comma
print ("The formatted output is : ")
print (', '.join(test_list))
```

**Output :**

```py
The original list is : ['Geeks', 'For', 'Geeks']
The formatted output is : 
Geeks, For, Geeks

```