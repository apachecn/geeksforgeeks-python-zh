# 在 Python 中创建集合字典

> 原文:[https://www . geesforgeks . org/creating-python 中的集合词典/](https://www.geeksforgeeks.org/creating-dictionary-of-sets-in-python/)

在本文中，我们将讨论如何用 Python 创建集合字典。

## 方法 1:天真的方法

我们可以通过将集合作为值传递给键来创建集合字典。

**语法:**

> {“键”:集合 1，“键”:集合 2，……..，“键”:设置 n}

**示例** : Python 程序，用于创建学生详细信息的集合字典

## 蟒蛇 3

```py
# create  dictionary of sets for student details
data = {'Student Roll-no': {1, 2, 3, 4, 5},
        'Student Aadhar No': {11, 22, 33, 44, 55}}

# display
print(data)
```

**输出:**

> {“学生人数”:{1，2，3，4，5},“学生人数”:{33，11，44，22，55}}

根据定义，集合不允许重复。

**示例 2:** Python 程序显示不允许重复

## 蟒蛇 3

```py
# create  dictionary of sets for student details
data = {'Student Roll-no': {1, 2, 3, 4, 5, 1, 2, 3, 2},
        'Student Aadhar No': {11, 22, 33, 44, 55, 22,
                              33, 44, 11}}

# display
print(data)
```

**输出:**

> {“学生人数”:{1，2，3，4，5},“学生人数”:{33，11，44，22，55}}

## **方法二:使用** [**默认方法**](https://www.geeksforgeeks.org/defaultdict-in-python/)

在这里，在这种方法中，我们将创建一个默认集，然后将键值传递给它。

**语法:**

> defaultdict(集)

**传递带有关键字和值的字典的语法:**

> dictionary _ name[" key "]| = { ' value 1 '，' value2 '，…………，' value n'}

哪里，

*   dictionary_name 是输入词典
*   关键是关键
*   值是集合

**示例:**创建学生数据集字典的 Python 代码

## 蟒蛇 3

```py
# import defaultdict module
from collections import defaultdict

# create an empty set of dictionary
dictionary = defaultdict(set)

# enter key value pair 1
dictionary["Student Roll-no"] |= {1, 2, 3, 4, 5}

# ennter key value pair 2
dictionary["Student Aadhar No"] |= {11, 22, 33, 44, 55}

# display
dictionary
```

**输出:**

> defaultdict(集，
> 
> { '学生编号':{11，22，33，44，55}，
> 
> 学生名单-编号:{1，2，3，4，5}})

## **方法三:使用** [**设置默认()方法**](https://www.geeksforgeeks.org/python-dictionary-setdefault-method/)

setdefault()方法返回字典中某个键的值。如果没有，它会向字典中插入一个带值的键。

**语法:**

> dict.setdefault(key，default_value)

哪里，

*   关键字–在字典中搜索的关键字。
*   default_value 是特定键的值

**示例:**将学生姓名集插入词典的 Python 程序

## 蟒蛇 3

```py
# Dictionary with student data
data = {'Student No': {1, 2, 3, 4, 5},
        'Student Aadhar No': {11, 22, 33, 44, 55}}

# using setdefault() method to get aadhar number
# of the students
print(data.setdefault('Student Aadhar No'))

# using setdefault() method to get aadhar number
# of the students
print(data.setdefault('Student No'))

# set the third set using setdefault method for 
# student names
data = data.setdefault(
    'Student Names', {'sravan', 'gopi', 'ramya',
                      'durga', 'sudheer'})

# display
data
```

**输出:**

> {33, 11, 44, 22, 55}
> 
> {1, 2, 3, 4, 5}
> 
> " durga "，" gopi "，" ramya "，" sravan "，" sud army " }