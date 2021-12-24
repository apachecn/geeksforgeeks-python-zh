# Python 中的命名图

> 原文:[https://www.geeksforgeeks.org/namedtuple-in-python/](https://www.geeksforgeeks.org/namedtuple-in-python/)

Python 支持一种类似于[字典](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)的容器，称为模块中的“ **namedtuple()** ”、[T5】集合](https://www.geeksforgeeks.org/python-collections-module/) 。像字典一样，它们包含散列到特定值的键。但相反，它支持从键值访问和迭代，这是字典所缺乏的功能。

**例:**

## 蟒 3

```
# Python code to demonstrate namedtuple()

from collections import namedtuple

# Declaring namedtuple()
Student = namedtuple('Student', ['name', 'age', 'DOB'])

# Adding values
S = Student('Nandini', '19', '2541997')

# Access using index
print("The Student age using index is : ", end="")
print(S[1])

# Access using name
print("The Student name using keyname is : ", end="")
print(S.name)
```

**输出:**

```
The Student age using index is : 19
The Student name using keyname is : Nandini
```

## **我们来看看 namedtuple()** 上的各种操作

## 访问操作

*   **按索引访问:**named tuple()的属性值是有序的，可以使用索引号进行访问，这与不能通过索引访问的字典不同。
*   **通过 keyname 访问:**通过 keyname 访问也是允许的，就像在字典中一样。
*   **使用 getattr():** 这是另一种访问值的方法，方法是将 namedtuple 和 key 值作为参数。

## 蟒蛇 3

```
# Python code to demonstrate namedtuple() and
# Access by name, index and getattr()

# importing "collections" for namedtuple()
import collections

# Declaring namedtuple()
Student = collections.namedtuple('Student', ['name', 'age', 'DOB'])

# Adding values
S = Student('Nandini', '19', '2541997')

# Access using index
print("The Student age using index is : ", end="")
print(S[1])

# Access using name
print("The Student name using keyname is : ", end="")
print(S.name)

# Access using getattr()
print("The Student DOB using getattr() is : ", end="")
print(getattr(S, 'DOB'))
```

**输出:**

```
The Student age using index is : 19
The Student name using keyname is : Nandini
The Student DOB using getattr() is : 2541997
```

## 转换操作

*   **_make() :-** 该函数用于从作为参数传递的可迭代中返回一个名为()的**。**
*   **_asdict() :-** 该函数返回**[**ordereddct()**](https://www.geeksforgeeks.org/ordereddict-in-python/)，该函数是根据 namedtuple()的映射值构造的。**
*   ****使用“**”(双星)运算符** :-该函数用于**将字典转换为名称元组()。****

## **蟒蛇 3**

```
# Python code to demonstrate namedtuple() and
# _make(), _asdict() and "**" operator

# importing "collections" for namedtuple()
import collections

# Declaring namedtuple()
Student = collections.namedtuple('Student',
                                 ['name', 'age', 'DOB'])

# Adding values
S = Student('Nandini', '19', '2541997')

# initializing iterable
li = ['Manjeet', '19', '411997']

# initializing dict
di = {'name': "Nikhil", 'age': 19, 'DOB': '1391997'}

# using _make() to return namedtuple()
print("The namedtuple instance using iterable is  : ")
print(Student._make(li))

# using _asdict() to return an OrderedDict()
print("The OrderedDict instance using namedtuple is  : ")
print(S._asdict())

# using ** operator to return namedtuple from dictionary
print("The namedtuple instance from dict is  : ")
print(Student(**di))
```

****输出:****

```
The namedtuple instance using iterable is  : 
Student(name='Manjeet', age='19', DOB='411997')
The OrderedDict instance using namedtuple is  : 
OrderedDict([('name', 'Nandini'), ('age', '19'), ('DOB', '2541997')])
The namedtuple instance from dict is  : 
Student(name='Nikhil', age=19, DOB='1391997')
```

## **附加操作**

*   ****_fields:** 该函数用于返回**所声明的名称空间的所有注释记号**。**
*   ****_replace():** _replace()与 str.replace()类似，但目标是命名字段(不修改原始值)**

## **计算机编程语言**

```
# Python code to demonstrate namedtuple() and
# _fields and _replace()

# importing "collections" for namedtuple()
import collections

# Declaring namedtuple()
Student = collections.namedtuple('Student', ['name', 'age', 'DOB'])

# Adding values
S = Student('Nandini', '19', '2541997')

# using _fields to display all the keynames of namedtuple()
print("All the fields of students are : ")
print(S._fields)

# ._replace returns a new namedtuple, it does not modify the original
print("returns a new namedtuple : ")
print(S._replace(name='Manjeet'))
# original namedtuple
print(S)
```

****输出:****

```
All the fields of students are : 
('name', 'age', 'DOB')
The modified namedtuple is : 
Student(name='Manjeet', age='19', DOB='2541997') 
```

**本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**