# python–etrtools . star map()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-etrtools-star map/

[itertools](https://www.geeksforgeeks.org/python-itertools/) 是 Python 中的一个模块，它有一组用于处理迭代器的函数。它们使得遍历像列表和字符串这样的数据项变得非常容易。其中一个 itertools 功能是**星图()**。
**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

## 星图()函数

当一个可迭代表包含在另一个可迭代表中，并且必须对其应用特定的函数时，使用 starmap()。starmap()将另一个可迭代表中的每个可迭代表元素视为一个单独的项目。它类似于 map()。该函数属于[终止迭代器](https://www.geeksforgeeks.org/python-itertools/#terminate)类别。
**语法:**

```
starmap(function, iterable)
```

该函数可以是内置函数、用户定义函数，甚至是 lambda 函数。要了解 map()和 starmap()之间的区别，请查看下面的代码片段:

## 蟒蛇 3

```
li =[(2, 5), (3, 2), (4, 3)]

new_li = list(map(pow, li))

print(new_li)
```

**Output:** 

```
TypeError Traceback (most recent call last)
 in 
      1 li=[(2, 5), (3, 2), (4, 3)]
----> 2 new_li=list(map(pow, li))
      3 print(new_li)

TypeError: pow expected at least 2 arguments, got 1
```

这里，映射将列表中的每个元组视为单个参数，因此会引发错误。星图()克服了这个问题。请看下面的代码片段:

## 蟒蛇 3

```
from itertools import starmap

li =[(2, 5), (3, 2), (4, 3)]

new_li = list(starmap(pow, li))

print(new_li)
```

**Output:** 

```
[32, 9, 64]
```

星图()的内部工作可以按如下方式实现。

```
def startmap(function, iterable):

   for it in iterables:
       yield function(*it)
```

这里的“它”也表示可重复的。
我们再来看一个区分 map()和 starmap()的例子。我们可以使用 map()对 iterable 中的每个元素应用一个函数。要说我们需要给列表中的每个元素添加一个常数，我们可以使用 map()。

## 蟒蛇 3

```
li =[2, 3, 4, 5, 6, 7]

# adds 2 to each element in list
ans = list(map(lambda x:x + 2, li))

print(ans)
```

**Output:** 

```
[4, 5, 6, 7, 8, 9]
```

**如果我们想给列表的不同元素添加不同的数字会怎么样？**
现在，必须使用星图()。

## 蟒蛇 3

```
from itertools import starmap

li =[(2, 3), (3, 1), (4, 6), (5, 3), (6, 5), (7, 2)]

ans = list(starmap(lambda x, y:x + y, li))

print(ans)
```

**Output:** 

```
[5, 4, 10, 8, 11, 9]
```

**使用星图()的实例:**
考虑一个包含各种三角形坐标的列表。我们应该应用毕达哥拉斯定理，找出哪个坐标构成直角三角形。可以按如下方式实现:

## 蟒蛇 3

```
from itertools import starmap

co_ordinates =[(2, 3, 4),
               (3, 4, 5),
               (6, 8, 10),
               (1, 5, 7),
               (7, 4, 10)]

# Set true if coordinates form
# a right-triangle else false
right_triangles = list(starmap(lambda x, y, z:True
                               if ((x * x)+(y * y))==(z * z)
                               else False, co_ordinates))

print("tuples which form right angled triangle :",
      right_triangles, end ="\n\n")

print("The right triangle coordinates are :",
      end ="")

# to print the coordinates
for i in range (0, len(right_triangles)):

    if right_triangles[i]== True:

        print(co_ordinates[i], end =" ")
```

**Output:**tuples which form right angled triangle : [False, True, True, False, False]The right triangle coordinates are :(3, 4, 5) (6, 8, 10)