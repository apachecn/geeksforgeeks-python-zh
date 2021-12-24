# Python–在列表中查找包含字符串的索引

> 原文:[https://www . geesforgeks . org/python-find-index-containing-string-in-list/](https://www.geeksforgeeks.org/python-find-index-containing-string-in-list/)

给定一个列表，任务是编写一个 Python 程序来查找包含字符串的索引。

**示例:**

> **输入:** ['sravan '，98，' harsha '，' jyothika '，' deepika '，78，90，' ramya']
> 
> **输出:** 0 2 3 4 7
> 
> **说明:**索引 0 2 3 4 7 只包含字符串。

## 方法 1:在 for 循环中使用[类型()运算符](https://www.geeksforgeeks.org/python-type-function/)

通过使用 type()运算符，我们可以从列表中获取字符串元素索引，字符串元素将位于 str()类型下，因此我们使用 for 循环遍历整个列表，并返回 string 类型的索引。

## 蟒蛇 3

```py
# create a list of names and marks
list1 = ['sravan', 98, 'harsha', 'jyothika', 
         'deepika', 78, 90, 'ramya']

# display
list1

# iterate through list of elemens
for i in list1:

    # check for type is str
    if(type(i) is str):

        # display index
        print(list1.index(i))
```

**输出:**

```py
0
2
3
4
7
```

## 方法二:在[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)中使用 type()运算符

通过使用列表理解，我们可以获得字符串元素的索引。

> **语法:**【列表中迭代器的 list.index(迭代器)如果(类型(迭代器)是 str)】

## 蟒蛇 3

```py
# create a list of names and marks
list1 = ['sravan', 98, 'harsha', 'jyothika', 
         'deepika', 78, 90, 'ramya']

# display
list1

# list comprehension
print([list1.index(i) for i in list1 if(type(i) is str)])

# list comprehension display strings
print([i for i in list1 if(type(i) is str)])
```

**输出:**

```py
[0, 2, 3, 4, 7]
['sravan', 'harsha', 'jyothika', 'deepika', 'ramya']
```