# Python 中的迭代器函数|集合 1

> 原文:[https://www . geesforgeks . org/iterator-functions-in-python-set-1/](https://www.geeksforgeeks.org/iterator-functions-in-python-set-1/)

perquisite:[Python 中的迭代器](https://www.geeksforgeeks.org/iterators-in-python/)
Python 在其定义中还允许一些有趣且有用的迭代器函数，以实现高效的循环并加快代码的执行速度。模块 **itertools** 中有很多内置迭代器。
这个模块实现了许多迭代器构建块。
**一些有用的迭代器:**
**1。累加(iter，func)** :-这个迭代器接受**两个参数，可迭代目标和在目标**中每次迭代值时要遵循的函数。如果没有函数通过，默认情况下会进行**添加**。如果输入表为空，输出表也将为空。
**2。链(iter1，iter2..)** :-该函数用于打印其参数中提到的可迭代目标中的所有**值。** 

## 计算机编程语言

```py
# Python code to demonstrate the working of
# accumulate() and chain()

# importing "itertools" for iterator operations
import itertools

# importing "operator" for operator operations
import operator

# initializing list 1
li1 = [1, 4, 5, 7]

# initializing list 2
li2 = [1, 6, 5, 9]

# initializing list 3
li3 = [8, 10, 5, 4]

# using accumulate()
# prints the successive summation of elements
print ("The sum after each iteration is : ",end="")
print (list(itertools.accumulate(li1)))

# using accumulate()
# prints the successive multiplication of elements
print ("The product after each iteration is : ",end="")
print (list(itertools.accumulate(li1,operator.mul)))

# using chain() to print all elements of lists
print ("All values in mentioned chain are : ",end="")
print (list(itertools.chain(li1,li2,li3)))
```

输出:

```py
The sum after each iteration is : [1, 5, 10, 17]
The product after each iteration is : [1, 4, 20, 140]
All values in mentioned chain are : [1, 4, 5, 7, 1, 6, 5, 9, 8, 10, 5, 4]
```

**3。chain.from_iterable()** :-该函数的实现方式与 chain()类似，但这里的参数是列表的**列表或任何其他可 iterable 容器**。
**4。compress(iter，selector)** :-这个迭代器**根据作为其他参数传递的布尔列表**值，有选择地从传递的容器**中挑选要打印的值**。打印布尔真对应的参数**，否则跳过所有参数。** 

## **计算机编程语言**

```py
# Python code to demonstrate the working of
# chain.from_iterable() and compress()

# importing "itertools" for iterator operations
import itertools

# initializing list 1
li1 = [1, 4, 5, 7]

# initializing list 2
li2 = [1, 6, 5, 9]

# initializing list 3
li3 = [8, 10, 5, 4]

# initializing list of list
li4 = [li1, li2, li3]

# using chain.from_iterable() to print all elements of lists
print ("All values in mentioned chain are : ",end="")
print (list(itertools.chain.from_iterable(li4)))

# using compress() selectively print data values
print ("The compressed values in string are : ",end="")
print (list(itertools.compress('GEEKSFORGEEKS',[1,0,0,0,0,1,0,0,1,0,0,0,0])))
```

**输出:** 

```py
All values in mentioned chain are : [1, 4, 5, 7, 1, 6, 5, 9, 8, 10, 5, 4]
The compressed values in string are : ['G', 'F', 'G']
```

****5。dropwhile(func，seq)** :-这个迭代器开始只打印 func 后面的字符**。in argument 第一次返回 false** 。
**6。filterfalse(func，seq)** :-顾名思义，**这个迭代器只打印为传递的函数返回 false** 的值。** 

## **计算机编程语言**

```py
# Python code to demonstrate the working of
# dropwhile() and filterfalse()

# importing "itertools" for iterator operations
import itertools

# initializing list
li = [2, 4, 5, 7, 8]

# using dropwhile() to start displaying after condition is false
print ("The values after condition returns false : ",end="")
print (list(itertools.dropwhile(lambda x : x%2==0,li)))

# using filterfalse() to print false values
print ("The values that return false to function are : ",end="")
print (list(itertools.filterfalse(lambda x : x%2==0,li)))
```

**输出:** 

```py
The values after condition returns false : [5, 7, 8]
The values that return false to function are : [5, 7]
```

****参考**:[https://docs.python.org/dev/library/itertools.html](https://docs.python.org/dev/library/itertools.html)T4】**

**本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。**