# Python 集合模块

> 原文:[https://www.geeksforgeeks.org/python-collections-module/](https://www.geeksforgeeks.org/python-collections-module/)

Python 中的集合模块提供了不同类型的容器。容器是一个对象，用于存储不同的对象，并提供一种方法来访问包含的对象并对其进行迭代。内置容器有[元组](https://www.geeksforgeeks.org/python-tuples/)、[列表](https://www.geeksforgeeks.org/python-list/)、[字典](https://www.geeksforgeeks.org/python-dictionary/)等。在本文中，我们将讨论集合模块提供的不同容器。

> **目录:**
> 
> *   [计数器](#counters)
> *   [订货合同](#ordereddict)
> *   [DefaultDict](#defaultdict)
> *   [链目录](#chainmap)
> *   [命名双](#namedtuple)
> *   从开始
> *   [UserDict](#userdict)
> *   [用户列表](#userlist)
> *   [用户字符串](#userstring)

## 计数器

A [计数器](https://www.geeksforgeeks.org/counters-in-python-set-1/)是字典的一个子类。它用于以无序字典的形式保存可迭代表中元素的计数，其中键表示可迭代表中的元素，值表示可迭代表中该元素的计数。

**注:**相当于其他语言的包或多集。

**语法:**

```py
class collections.Counter([iterable-or-mapping])
```

### 初始化计数器对象

可以使用 counter()函数初始化 counter 对象，并且可以通过以下方式之一调用该函数:

*   带有一系列项目
*   带有包含键和计数的字典
*   关键字参数将字符串名称映射到计数

**示例:**

## 蟒蛇 3

```py
# A Python program to show different
# ways to create Counter
from collections import Counter

# With sequence of items 
print(Counter(['B','B','A','B','C','A','B',
               'B','A','C']))

# with dictionary
print(Counter({'A':3, 'B':5, 'C':2}))

# with keyword arguments
print(Counter(A=3, B=5, C=2))
```

**输出:**

```py
Counter({'B': 5, 'A': 3, 'C': 2})
Counter({'B': 5, 'A': 3, 'C': 2})
Counter({'B': 5, 'A': 3, 'C': 2})
```

**注意:**更多信息请参考 Python 中的[计数器。](https://www.geeksforgeeks.org/counters-in-python-set-1/)

## OrderedDict

一个[ordereddct](https://www.geeksforgeeks.org/ordereddict-in-python/)也是字典的一个子类，但是不像字典，它记住了键插入的顺序。

**语法:**

```py
class collections.OrderDict()
```

**示例:**

## 蟒蛇 3

```py
# A Python program to demonstrate working
# of OrderedDict

from collections import OrderedDict

print("This is a Dict:\n")
d = {}
d['a'] = 1
d['b'] = 2
d['c'] = 3
d['d'] = 4

for key, value in d.items():
    print(key, value)

print("\nThis is an Ordered Dict:\n")
od = OrderedDict()
od['a'] = 1
od['b'] = 2
od['c'] = 3
od['d'] = 4

for key, value in od.items():
    print(key, value)
```

**输出:**

```py
This is a Dict:

a 1
b 2
c 3
d 4

This is an Ordered Dict:

a 1
b 2
c 3
d 4
```

而删除和重新插入同一个键会将键推到最后，以保持键的插入顺序。

**示例:**

## 蟒蛇 3

```py
# A Python program to demonstrate working
# of OrderedDict

from collections import OrderedDict

od = OrderedDict()
od['a'] = 1
od['b'] = 2
od['c'] = 3
od['d'] = 4

print('Before Deleting')
for key, value in od.items():
    print(key, value)

# deleting element
od.pop('a')

# Re-inserting the same
od['a'] = 1

print('\nAfter re-inserting')
for key, value in od.items():
    print(key, value)
```

**输出:**

```py
Before Deleting
a 1
b 2
c 3
d 4

After re-inserting
b 2
c 3
d 4
a 1
```

**注意:**更多信息请参考 Python 中的[ordereddct](https://www.geeksforgeeks.org/ordereddict-in-python/)

## DefaultDict(预设字典)

A [DefaultDict](https://www.geeksforgeeks.org/defaultdict-in-python/) 也是字典的一个子类。它用于为不存在且从不引发键错误的键提供一些默认值。

**语法:**

```py
class collections.defaultdict(default_factory)
```

default_factory 是一个为创建的字典提供默认值的函数。如果此参数不存在，则会引发键错误。

### 初始化默认字典对象

通过将数据类型作为参数传递，可以使用 DefaultDict()方法初始化 DefaultDict 对象。

**示例:**

## 蟒蛇 3

```py
# Python program to demonstrate
# defaultdict

from collections import defaultdict

# Defining the dict
d = defaultdict(int)

L = [1, 2, 3, 4, 2, 4, 1, 2]

# Iterate through the list
# for keeping the count
for i in L:

    # The default value is 0
    # so there is no need to 
    # enter the key first
    d[i] += 1

print(d)
```

**输出:**

```py
defaultdict(<class 'int'>, {1: 2, 2: 3, 3: 1, 4: 2})
```

**例 2:**

## 蟒蛇 3

```py
# Python program to demonstrate
# defaultdict

from collections import defaultdict

# Defining a dict
d = defaultdict(list)

for i in range(5):
    d[i].append(i)

print("Dictionary with values as list:")
print(d)
```

**输出:**

> 值为列表的字典:
> defaultdict( <类“列表”>，{0: [0]，1: [1]，2: [2]，3: [3]，4: [4]})

**注意:**更多信息请参考 Python 中的[default dict](https://www.geeksforgeeks.org/defaultdict-in-python/)

## 主席

A [ChainMap](https://www.geeksforgeeks.org/chainmap-in-python/) 将许多词典封装成一个单元，并返回一个词典列表。

**语法:**

```py
class collections.ChainMap(dict1, dict2)
```

**示例:**

## 蟒蛇 3

```py
# Python program to demonstrate
# ChainMap

from collections import ChainMap

d1 = {'a': 1, 'b': 2}
d2 = {'c': 3, 'd': 4}
d3 = {'e': 5, 'f': 6}

# Defining the chainmap
c = ChainMap(d1, d2, d3)

print(c)
```

**输出:**

```py
ChainMap({'a': 1, 'b': 2}, {'c': 3, 'd': 4}, {'e': 5, 'f': 6})
```

### 从链图访问键和值

可以使用键名访问链映射中的值。也可以使用 key()和 values()方法访问它们。

**示例:**

## 蟒蛇 3

```py
# Python program to demonstrate
# ChainMap

from collections import ChainMap

d1 = {'a': 1, 'b': 2}
d2 = {'c': 3, 'd': 4}
d3 = {'e': 5, 'f': 6}

# Defining the chainmap
c = ChainMap(d1, d2, d3)

# Accessing Values using key name
print(c['a'])

# Accessing values using values()
# method
print(c.values())

# Accessing keys using keys()
# method
print(c.keys())
```

**输出:**

> 1
> value svew(chain map({ a:1 '，' b ':' 2 '，{ ' c ':' 3 '，' d '，{ ' e ':' 5 '，' f ':))))
> keysvew(chain map({ a:{ ' 1 '，' b ':' 2 }，{ ' c ':' 3 '，' d ':' 4 '，{ ' e ':' 5 '，' f ')

### 添加新词典

可以使用 **new_child()** 方法添加新词典。新添加的词典将添加到链图的开头。

**示例:**

## 蟒蛇 3

```py
# Python code to demonstrate ChainMap and
# new_child()

import collections

# initializing dictionaries
dic1 = { 'a' : 1, 'b' : 2 }
dic2 = { 'b' : 3, 'c' : 4 }
dic3 = { 'f' : 5 }

# initializing ChainMap
chain = collections.ChainMap(dic1, dic2)

# printing chainMap
print ("All the ChainMap contents are : ")
print (chain)

# using new_child() to add new dictionary
chain1 = chain.new_child(dic3)

# printing chainMap
print ("Displaying new ChainMap : ")
print (chain1)
```

**输出:**

```py
All the ChainMap contents are : 
ChainMap({'a': 1, 'b': 2}, {'b': 3, 'c': 4})
Displaying new ChainMap : 
ChainMap({'f': 5}, {'a': 1, 'b': 2}, {'b': 3, 'c': 4})
```

**注意:**更多信息请参考 Python 中的[链图](https://www.geeksforgeeks.org/chainmap-in-python/)

## 名为双

一个[命名元组](https://www.geeksforgeeks.org/namedtuple-in-python/)返回一个元组对象，其中包含普通元组缺少的每个位置的名称。例如，考虑一个名为 student 的元组，其中第一个元素代表 fname，第二个元素代表 lname，第三个元素代表 DOB。假设为了调用 fname 而不是记住索引位置，您实际上可以通过使用 fname 参数来调用元素，那么访问元组元素将非常容易。该功能由名为“耦合”的提供。

**语法:**

```py
class collections.namedtuple(typename, field_names)
```

**示例:**

## 蟒蛇 3

```py
# Python code to demonstrate namedtuple()

from collections import namedtuple

# Declaring namedtuple()
Student = namedtuple('Student',['name','age','DOB'])

# Adding values
S = Student('Nandini','19','2541997')

# Access using index
print ("The Student age using index is : ",end ="")
print (S[1])

# Access using name 
print ("The Student name using keyname is : ",end ="")
print (S.name)
```

**输出:**

```py
The Student age using index is : 19
The Student name using keyname is : Nandini
```

### 转换操作

**1。_make():** 该函数用于从作为参数传递的 iterable 返回一个 namedtuple()。

**2。_asdict():** 该函数返回**[命令()](https://www.geeksforgeeks.org/ordereddict-in-python/)，该命令是根据 namedtuple()的映射值构造的。**

****示例:****

## **蟒蛇 3**

```py
# Python code to demonstrate namedtuple() and
# _make(), _asdict()

from collections import namedtuple

# Declaring namedtuple()
Student = namedtuple('Student',['name','age','DOB'])

# Adding values
S = Student('Nandini','19','2541997')

# initializing iterable 
li = ['Manjeet', '19', '411997' ]

# initializing dict
di = { 'name' : "Nikhil", 'age' : 19 , 'DOB' : '1391997' }

# using _make() to return namedtuple()
print ("The namedtuple instance using iterable is  : ")
print (Student._make(li))

# using _asdict() to return an OrderedDict()
print ("The OrderedDict instance using namedtuple is  : ")
print (S._asdict())
```

****输出:****

```py
The namedtuple instance using iterable is  : 
Student(name='Manjeet', age='19', DOB='411997')
The OrderedDict instance using namedtuple is  : 
OrderedDict([('name', 'Nandini'), ('age', '19'), ('DOB', '2541997')])
```

****注:**更多信息请参考 Python 中[命名图](https://www.geeksforgeeks.org/namedtuple-in-python/)**

## **双端队列**

**[Deque(双端队列)](https://www.geeksforgeeks.org/deque-in-python/)是一个优化列表，用于从容器的两侧进行更快的追加和弹出操作。与时间复杂度为 0(n)的列表相比，它为追加和弹出操作提供了 0(1)的时间复杂度。**

****语法:****

```py
class collections.deque(list)
```

**该函数将列表作为参数。**

****示例:****

## **蟒蛇 3**

```py
# Python code to demonstrate deque

from collections import deque

# Declaring deque
queue = deque(['name','age','DOB'])

print(queue)
```

****输出:****

```py
deque(['name', 'age', 'DOB'])
```

### **插入元素**

**deque 中的元素可以从两端插入。使用方法从右追加插入元素，使用方法从左追加插入元素。**

****示例:****

## **蟒蛇 3**

```py
# Python code to demonstrate working of 
# append(), appendleft()

from collections import deque

# initializing deque
de = deque([1,2,3])

# using append() to insert element at right end 
# inserts 4 at the end of deque
de.append(4)

# printing modified deque
print ("The deque after appending at right is : ")
print (de)

# using appendleft() to insert element at right end 
# inserts 6 at the beginning of deque
de.appendleft(6)

# printing modified deque
print ("The deque after appending at left is : ")
print (de)
```

****输出:****

```py
The deque after appending at right is : 
deque([1, 2, 3, 4])
The deque after appending at left is : 
deque([6, 1, 2, 3, 4])
```

### **移除元素**

**元素也可以从两端移除。若要从右侧移除元素，请使用 pop()方法；若要从左侧移除元素，请使用 popleft()方法。**

****示例:****

## **蟒蛇 3**

```py
# Python code to demonstrate working of 
# pop(), and popleft()

from collections import deque

# initializing deque
de = deque([6, 1, 2, 3, 4])

# using pop() to delete element from right end 
# deletes 4 from the right end of deque
de.pop()

# printing modified deque
print ("The deque after deleting from right is : ")
print (de)

# using popleft() to delete element from left end 
# deletes 6 from the left end of deque
de.popleft()

# printing modified deque
print ("The deque after deleting from left is : ")
print (de)
```

****输出:****

```py
The deque after deleting from right is : 
deque([6, 1, 2, 3])
The deque after deleting from left is : 
deque([1, 2, 3])
```

****注:**更多信息请参考 Python 中的[德格。](https://www.geeksforgeeks.org/deque-in-python/)**

## **UserDict(用户字典)**

**[UserDict](https://www.geeksforgeeks.org/collections-userdict-in-python/) 是一个类似字典的容器，充当字典对象的包装器。当有人想要创建他们自己的带有一些修改过的或新的功能的字典时，使用这个容器。**

****语法:****

```py
class collections.UserDict([initialdata])
```

****示例:****

## **蟒蛇 3**

```py
# Python program to demonstrate
# userdict

from collections import UserDict

# Creating a Dictionary where
# deletion is not allowed
class MyDict(UserDict):

    # Function to stop deletion
    # from dictionary
    def __del__(self):
        raise RuntimeError("Deletion not allowed")

    # Function to stop pop from 
    # dictionary
    def pop(self, s = None):
        raise RuntimeError("Deletion not allowed")

    # Function to stop popitem 
    # from Dictionary
    def popitem(self, s = None):
        raise RuntimeError("Deletion not allowed")

# Driver's code
d = MyDict({'a':1,
    'b': 2,
    'c': 3})

d.pop(1)
```

****输出:****

```py
Traceback (most recent call last):
  File "/home/f8db849e4cf1e58177983b2b6023c1a3.py", line 32, in <module>
    d.pop(1) 
  File "/home/f8db849e4cf1e58177983b2b6023c1a3.py", line 20, in pop
    raise RuntimeError("Deletion not allowed") 
RuntimeError: Deletion not allowed
Exception ignored in: <bound method MyDict.__del__ of {'a': 1, 'b': 2, 'c': 3}>
Traceback (most recent call last):
  File "/home/f8db849e4cf1e58177983b2b6023c1a3.py", line 15, in __del__
RuntimeError: Deletion not allowed
```

**注:更多信息请参考 Python 中的[用户字典](https://www.geeksforgeeks.org/collections-userdict-in-python/)**

## **用户列表**

**[用户列表](https://www.geeksforgeeks.org/collections-userlist-in-python/)是一个类似于容器的列表，充当列表对象的包装器。当有人想要创建他们自己的带有一些修改或附加功能的列表时，这很有用。**

****语法:****

```py
class collections.UserList([list])
```

****示例:****

## **蟒蛇 3**

```py
# Python program to demonstrate
# userlist

from collections import UserList

# Creating a List where
# deletion is not allowed
class MyList(UserList):

    # Function to stop deletion
    # from List
    def remove(self, s = None):
        raise RuntimeError("Deletion not allowed")

    # Function to stop pop from 
    # List
    def pop(self, s = None):
        raise RuntimeError("Deletion not allowed")

# Driver's code
L = MyList([1, 2, 3, 4])

print("Original List")

# Inserting to List"
L.append(5)
print("After Insertion")
print(L)

# Deleting From List
L.remove()
```

****输出:****

```py
Original List
After Insertion
[1, 2, 3, 4, 5]
```

```py
Traceback (most recent call last):
  File "/home/c90487eefa7474c0566435269f50a52a.py", line 33, in <module>
    L.remove() 
  File "/home/c90487eefa7474c0566435269f50a52a.py", line 15, in remove
    raise RuntimeError("Deletion not allowed") 
RuntimeError: Deletion not allowed
```

****注意:**更多信息请参考 Python 中的[用户列表](https://www.geeksforgeeks.org/collections-userlist-in-python/)**

## **用户字符串**

**[用户字符串](https://www.geeksforgeeks.org/collections-userstring-in-python/)是一个类似于容器的字符串，就像用户字典和用户列表一样，它充当字符串对象的包装器。当有人想要创建他们自己的带有一些修改或附加功能的字符串时，就会用到它。**

****语法:****

```py
class collections.UserString(seq)
```

****示例:****

## **蟒蛇 3**

```py
# Python program to demonstrate
# userstring

from collections import UserString

# Creating a Mutable String
class Mystring(UserString):

    # Function to append to
    # string
    def append(self, s):
        self.data += s

    # Function to remove from 
    # string
    def remove(self, s):
        self.data = self.data.replace(s, "")

# Driver's code
s1 = Mystring("Geeks")
print("Original String:", s1.data)

# Appending to string
s1.append("s")
print("String After Appending:", s1.data)

# Removing from string
s1.remove("e")
print("String after Removing:", s1.data)
```

****输出:****

```py
Original String: Geeks
String After Appending: Geekss
String after Removing: Gkss
```

****注意:**更多信息请参考 Python 中的[用户字符串](https://www.geeksforgeeks.org/collections-userstring-in-python/)**