# Python |串联字符串列表中的 N 个连续元素

> 原文:[https://www . geesforgeks . org/python-concatenate-n-continuous-in-elements-in-string-list/](https://www.geeksforgeeks.org/python-concatenate-n-consecutive-elements-in-string-list/)

有时，在处理数据时，我们会遇到一个问题，即我们需要在字符串列表中执行 N 个连续字符串的连接。这可以有许多跨域的应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`format() + zip() + iter()` +列表理解**
以上方法的组合可以用来执行这个特定的任务。在本例中，我们使用 zip()和 iter()执行分组任务，format()用于指定分组分隔符。

```py
# Python3 code to demonstrate working of
# Consecutive N concatenation in String list
# using format() + zip() + iter() + list comprehension

# initialize list 
test_list = ['gfg', 'is', 'good', 'for', 'geek', 'people']

# printing original list 
print("The original list : " + str(test_list))

# initialize N 
N = 3

# Consecutive N concatenation in String list
# using format() + zip() + iter() + list comprehension
temp = '{} ' * N 
res = [temp.format(*ele) for ele in zip(*[iter(test_list)] * N)]

# printing result
print("List after N concatenation of String : " + str(res))
```

**Output :**

```py
The original list : ['gfg', 'is', 'good', 'for', 'geek', 'people']
List after N concatenation of String : ['gfg is good ', 'for geek people ']

```