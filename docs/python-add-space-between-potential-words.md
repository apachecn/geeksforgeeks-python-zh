# Python–在潜在单词之间添加空格

> 原文:[https://www . geesforgeks . org/python-add-潜在单词之间的空格/](https://www.geeksforgeeks.org/python-add-space-between-potential-words/)

给定字符串列表，任务是在以大写字母开头的序列前添加一个空格。

> **输入**:test _ list =[“gfg Best”，“forGeeks”，“and computersciencestudents”]
> **输出**:[‘gfg Best’，‘for Geeks’，‘and Computer Science Students’]
> **解释**:用大写字母分隔的单词。
> 
> **输入**:test _ list =【“computerscience studentslovefg”】
> **输出**:【‘计算机专业学生爱 Gfg’】
> **解释**:大写字母分隔的单词。

**方法#1:使用循环+连接()**

这是执行这项任务的方法之一。在这种情况下，我们执行的任务是迭代所有的刺，然后是所有的字符，然后使用循环以暴力的方式添加空间。isupper()用于检查大写字符。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Add Space between Potential Words
# Using loop + join()

# initializing list
test_list = ["gfgBest", "forGeeks", "andComputerScience"]

# printing original list
print("The original list : " + str(test_list))

res = []

# loop to iterate all strings
for ele in test_list:
    temp = [[]]
    for char in ele:

        # checking for upper case character
        if char.isupper():
            temp.append([])

        # appending character at latest list
        temp[-1].append(char)

    # joining lists after adding space
    res.append(' '.join(''.join(ele) for ele in temp))

# printing result
print("The space added list of strings : " + str(res))
```

**Output**

```py
The original list : ['gfgBest', 'forGeeks', 'andComputerScience']
The space added list of strings : ['gfg Best', 'for Geeks', 'and Computer Science']
```

**方法 2:使用正则表达式()+列表理解**

上述功能的组合也可以用来解决这个问题。在本文中，我们使用正则表达式代码来检查大写字母，并使用列表理解来执行空格添加和连接。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Add Space between Potential Words
# Using regex() + list comprehension
import re

# initializing list
test_list = ["gfgBest", "forGeeks", "andComputerScience"]

# printing original list
print("The original list : " + str(test_list))

# using regex() to perform task
res = [re.sub(r"(\w)([A-Z])", r"\1 \2", ele) for ele in test_list]

# printing result
print("The space added list of strings : " + str(res))
```

**Output**

```py
The original list : ['gfgBest', 'forGeeks', 'andComputerScience']
The space added list of strings : ['gfg Best', 'for Geeks', 'and Computer Science']
```