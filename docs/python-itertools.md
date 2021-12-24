# Python 迭代器

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-etrtools/

Python 的 Itertool 是一个模块，它提供了各种在迭代器上工作的函数来产生复杂的迭代器。该模块作为一种快速、高效的内存工具，可以单独使用，也可以组合使用，形成**迭代器代数**。
例如，让我们假设有两个列表，您想要增加它们的元素。有几种方法可以实现这一点。可以使用简单的方法，即同时遍历列表中的两个元素，并将它们相乘。另一种方法是使用映射函数，即将 mul 运算符作为第一个参数传递给映射函数，将 Lists 作为第二个和第三个参数传递给该函数。让我们看看每种方法花费的时间。

## 蟒蛇 3

```
# Python program to demonstrate
# iterator module

import operator
import time

# Defining lists
L1 = [1, 2, 3]
L2 = [2, 3, 4]

# Starting time before map
# function
t1 = time.time()

# Calculating result
a, b, c = map(operator.mul, L1, L2)

# Ending time after map
# function
t2 = time.time()

# Time taken by map function
print("Result:", a, b, c)
print("Time taken by map function: %.6f" %(t2 - t1))

# Starting time before naive
# method
t1 = time.time()

# Calculating result using for loop
print("Result:", end = " ")
for i in range(3):
    print(L1[i] * L2[i], end = " ")

# Ending time after naive
# method
t2 = time.time()
print("\nTime taken by for loop: %.6f" %(t2 - t1))
```

**输出:**

```
Result: 2 6 12
Time taken by map function: 0.000005
Result: 2 6 12 
Time taken by for loop: 0.000014
```

在上面的例子中，可以看到 map 函数花费的时间大约是 for 循环花费的时间的一半。这表明 itertools 是快速、内存高效的工具。

**该模块提供的不同类型的迭代器有:**

*   [无限迭代器](#infinite)
*   [组合迭代器](#combine)
*   [终止迭代器](#terminate)

### 无限迭代器

Python 中的迭代器是可以与“for in loop”一起使用的任何 Python 类型。Python 列表、元组、字典和集合都是内置迭代器的例子。但是迭代器对象不必用尽，有时它可以是无限的。这种类型的迭代器被称为**无限迭代器**。

Python 提供三种类型的无限迭代器:

*   **计数(开始，步骤):**这个迭代器**从“开始”号开始打印，无限打印**。如果提到步骤，则跳过这些数字，否则默认情况下步骤为 1。请参见下面的示例，了解它与 for in 循环的用法。
    **例:**

## 蟒蛇 3

```
# Python program to demonstrate
# infinite iterators

import itertools

# for in loop
for i in itertools.count(5, 5):
    if i == 35:
        break
    else:
        print(i, end =" ")
```

**输出:**

```
5 10 15 20 25 30
```

*   **循环(可迭代):**这个迭代器从传递的容器中按顺序打印所有的值。当所有元素以循环方式打印时，它会重新开始**打印。
    **例 1:****

## 蟒蛇 3

```
# Python program to demonstrate
# infinite iterators

import itertools

count = 0

# for in loop
for i in itertools.cycle('AB'):
    if count > 7:
        break
    else:
        print(i, end = " ")
        count += 1
```

**输出:**

```
A B A B A B A B 
```

**示例 2:** 使用下一个函数。

## 蟒蛇 3

```
# Python program to demonstrate
# infinite iterators

import itertools

l = ['Geeks', 'for', 'Geeks']

# defining iterator
iterators = itertools.cycle(l)

# for in loop
for i in range(6):

    # Using next function
    print(next(iterators), end = " ")
```

组合迭代器
T1】输出:

```
Geeks for Geeks Geeks for Geeks 
```

*   **重复(val，num):** 这个迭代器重复打印传递的值无数次。如果提到可选关键字 num，那么它会重复打印 num 的次数。
    T3】例:

## 蟒蛇 3

```
# Python code to demonstrate the working of  
# repeat() 

# importing "itertools" for iterator operations 
import itertools 

# using repeat() to repeatedly print number 
print ("Printing the numbers repeatedly : ") 
print (list(itertools.repeat(25, 4)))
```

**输出:**

```
Printing the numbers repeatedly : 
[25, 25, 25, 25]
```

### 组合迭代器

用于简化组合结构(如排列、组合和笛卡尔乘积)的递归生成器称为组合迭代器。
Python 中有 4 个组合迭代器:

*   **乘积():**该工具**计算输入项的笛卡尔乘积**。为了计算一个可重复项与其自身的乘积，我们使用可选的 repeat 关键字参数来指定重复次数。这个函数的输出是按排序顺序排列的元组。
    **例:**

## 蟒蛇 3

```
# import the product function from itertools module
from itertools import product

print("The cartesian product using repeat:")
print(list(product([1, 2], repeat = 2)))
print()

print("The cartesian product of the containers:")
print(list(product(['geeks', 'for', 'geeks'], '2')))
print()

print("The cartesian product of the containers:")
print(list(product('AB', [3, 4])))
```

**输出:**

```
The cartesian product using repeat:
[(1, 1), (1, 2), (2, 1), (2, 2)]

The cartesian product of the containers:
[('geeks', '2'), ('for', '2'), ('geeks', '2')]

The cartesian product of the containers:
[('A', 3), ('A', 4), ('B', 3), ('B', 4)]
```

*   **置换():**置换()顾名思义就是用来**生成可迭代**的所有可能的置换。所有元素都是基于它们的位置而不是它们的价值被视为唯一的。此函数采用可迭代和 group_size，如果 group_size 的值未指定或等于 None，那么 group_size 的值将成为可迭代的长度。
    **例:**

## 蟒蛇 3

```
# import the product function from itertools module
from itertools import permutations

print ("All the permutations of the given list is:") 
print (list(permutations([1, 'geeks'], 2)))
print()
  Terminating iterators
print ("All the permutations of the given string is:") 
print (list(permutations('AB')))
print()

print ("All the permutations of the given container is:") 
print(list(permutations(range(3), 2)))
```

**输出:**

```
All the permutations of the given list is:
[(1, 'geeks'), ('geeks', 1)]

All the permutations of the given string is:
[('A', 'B'), ('B', 'A')]

All the permutations of the given container is:
[(0, 1), (0, 2), (1, 0), (1, 2), (2, 0), (2, 1)]
```

*   **组合():**这个迭代器按照排序顺序打印**在指定组大小的参数中传递的容器的所有可能组合(没有替换)**。
    **例:**

## 蟒蛇 3

```
# import combinations from itertools module

from itertools import combinations

print ("All the combination of list in sorted order(without replacement) is:") 
print(list(combinations(['A', 2], 2)))
print()

print ("All the combination of string in sorted order(without replacement) is:")
print(list(combinations('AB', 2)))
print()

print ("All the combination of list in sorted order(without replacement) is:")
print(list(combinations(range(2), 1)))
```

**输出:**

```
All the combination of list in sorted order(without replacement) is:
[('A', 2)]

All the combination of string in sorted order(without replacement) is:
[('A', 'B')]

All the combination of list in sorted order(without replacement) is:
[(0, ), (1, )]
```

*   **Combinations _ with _ replacement():**这个函数从 iterable 的元素中返回一个长度为 n 的子序列，其中 n 是这个函数用来确定这个函数生成的子序列的长度的参数。**单个元素可以在具有替换功能的组合中重复出现**。
    **例:**

## 蟒蛇 3

```
# import combinations from itertools module

from itertools import combinations_with_replacement

print ("All the combination of string in sorted order(with replacement) is:")
print(list(combinations_with_replacement("AB", 2)))
print()

print ("All the combination of list in sorted order(with replacement) is:")
print(list(combinations_with_replacement([1, 2], 2)))
print()

print ("All the combination of container in sorted order(with replacement) is:")
print(list(combinations_with_replacement(range(2), 1)))
```

**输出:**

```
All the combination of string in sorted order(with replacement) is:
[('A', 'A'), ('A', 'B'), ('B', 'B')]

All the combination of list in sorted order(with replacement) is:
[(1, 1), (1, 2), (2, 2)]

All the combination of container in sorted order(with replacement) is:
[(0, ), (1, )]Terminating iterators
```

### 终止迭代器

终止迭代器用于处理短输入序列，并根据所用方法的功能产生输出。

不同类型的终止迭代器有:

*   **累加(iter，func):** 这个迭代器接受两个参数，ITER target 和 target 中值每次迭代时要遵循的函数。如果没有传递函数，默认情况下会发生加法。如果输入表为空，输出表也将为空。
    T3】例:

## 蟒蛇 3

```
# Python code to demonstrate the working of 
# accumulate()

import itertools
import operator

# initializing list 1
li1 = [1, 4, 5, 7]

# using accumulate()
# prints the successive summation of elements
print ("The sum after each iteration is : ", end ="")
print (list(itertools.accumulate(li1)))

# using accumulate()
# prints the successive multiplication of elements
print ("The product after each iteration is : ", end ="")
print (list(itertools.accumulate(li1, operator.mul)))

# using accumulate()
# prints the successive summation of elements
print ("The sum after each iteration is : ", end ="")
print (list(itertools.accumulate(li1)))

# using accumulate()
# prints the successive multiplication of elements
print ("The product after each iteration is : ", end ="")
print (list(itertools.accumulate(li1, operator.mul)))
```

**输出:**

```
The sum after each iteration is : [1, 5, 10, 17]
The product after each iteration is : [1, 4, 20, 140]
The sum after each iteration is : [1, 5, 10, 17]
The product after each iteration is : [1, 4, 20, 140]
```

*   **链(iter1，iter2..):**此函数用于打印其参数中提到的可迭代目标中的所有值。
    T3】例:

## 蟒蛇 3

```
# Python code to demonstrate the working of 
# and chain()

import itertools

# initializing list 1
li1 = [1, 4, 5, 7]

# initializing list 2
li2 = [1, 6, 5, 9]

# initializing list 3
li3 = [8, 10, 5, 4]

# using chain() to print all elements of lists
print ("All values in mentioned chain are : ", end ="")
print (list(itertools.chain(li1, li2, li3)))
```

**输出:**

```
All values in mentioned chain are : [1, 4, 5, 7, 1, 6, 5, 9, 8, 10, 5, 4]
```

*   **chain.from_iterable():** 这个函数类似于 chain()实现，但这里的参数是列表列表或任何其他可 iterable 容器。
    T3】例:

## 蟒蛇 3

```
# Python code to demonstrate the working of 
# chain.from_iterable()

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
print ("All values in mentioned chain are : ", end ="")
print (list(itertools.chain.from_iterable(li4)))
```

**输出:**

```
All values in mentioned chain are : [1, 4, 5, 7, 1, 6, 5, 9, 8, 10, 5, 4]
```

*   **compress(iter，selector):** 这个迭代器根据作为其他参数传递的布尔列表值，有选择地从传递的容器中挑选要打印的值。打印对应于布尔真的参数，否则跳过所有参数。
    T3】例:

## 蟒蛇 3

```
# Python code to demonstrate the working of 
# and compress()

import itertools

# using compress() selectively print data values
print ("The compressed values in string are : ", end ="")
print (list(itertools.compress('GEEKSFORGEEKS', [1, 0, 0, 0, 0, 1, 0, 0, 1, 0, 0, 0, 0])))
```

**输出:**

```
The compressed values in string are : ['G', 'F', 'G']
```

*   **dropwhile(func，seq):** 这个迭代器只在 func 之后开始打印字符。in 参数第一次返回 false。
    T3】例:

## 蟒蛇 3

```
# Python code to demonstrate the working of 
# dropwhile()

import itertools

# initializing list 
li = [2, 4, 5, 7, 8]

# using dropwhile() to start displaying after condition is false
print ("The values after condition returns false : ", end ="")
print (list(itertools.dropwhile(lambda x : x % 2 == 0, li)))
```

**输出:**

```
The values after condition returns false : [5, 7, 8]
```

*   **filterfalse(func，seq):** 顾名思义，这个迭代器只打印为传递的函数返回 false 的值。
    T3】例:

## 蟒蛇 3

```
# Python code to demonstrate the working of 
# filterfalse()

import itertools

# initializing list 
li = [2, 4, 5, 7, 8]

# using filterfalse() to print false values
print ("The values that return false to function are : ", end ="")
print (list(itertools.filterfalse(lambda x : x % 2 == 0, li)))
```

**输出:**

```
The values that return false to function are : [5, 7]
```

*   **islice(iterable，start，stop，step):** 这个迭代器有选择地打印作为参数传递的 iterable 容器中提到的值。这个迭代器接受 4 个参数，可迭代容器，起始位置。，结束位置和步骤。
    T3】例:

## 蟒蛇 3

```
# Python code to demonstrate the working of 
# islice()

import itertools

# initializing list 
li = [2, 4, 5, 7, 8, 10, 20]

# using islice() to slice the list acc. to need
# starts printing from 2nd index till 6th skipping 2
print ("The sliced list values are : ", end ="")
print (list(itertools.islice(li, 1, 6, 2)))
```

**输出:**

```
The sliced list values are : [4, 7, 10]
```

*   **星图(func。，元组列表):**这个迭代器以一个函数和元组列表作为参数，从列表的每个元组中根据函数返回值。
    T3】例:

## 蟒蛇 3

```
# Python code to demonstrate the working of 
# starmap()

import itertools

# initializing tuple list
li = [ (1, 10, 5), (8, 4, 1), (5, 4, 9), (11, 10, 1) ]

# using starmap() for selection value acc. to function
# selects min of all tuple values
print ("The values acc. to function are : ", end ="")
print (list(itertools.starmap(min, li)))
```

**输出:**

```
The values acc. to function are : [1, 1, 4, 1]
```

*   **takewhile(func，iterable):** 这个迭代器与 dropwhile()相反，它打印值，直到函数第一次返回 false。
    T3】例:

## 蟒蛇 3

```
# Python code to demonstrate the working of 
# takewhile()

import itertools

# initializing list 
li = [2, 4, 6, 7, 8, 10, 20]

# using takewhile() to print values till condition is false.
print ("The list values till 1st false value are : ", end ="")
print (list(itertools.takewhile(lambda x : x % 2 == 0, li )))
```

**输出:**

```
The list values till 1st false value are : [2, 4, 6]
```

*   **tee(迭代器，计数):-** 这个迭代器将容器拆分成参数中提到的多个迭代器。
    T3】例:

## 蟒蛇 3

```
# Python code to demonstrate the working of 
# tee()

import itertools

# initializing list 
li = [2, 4, 6, 7, 8, 10, 20]

# storing list in iterator
iti = iter(li) 

# using tee() to make a list of iterators
# makes list of 3 iterators having same values.
it = itertools.tee(iti, 3)

# printing the values of iterators
print ("The iterators are : ")
for i in range (0, 3):
    print (list(it[i]))
```

**输出:**

```
The iterators are : 
[2, 4, 6, 7, 8, 10, 20]
[2, 4, 6, 7, 8, 10, 20]
[2, 4, 6, 7, 8, 10, 20]
```

*   **zip _ long(iterable 1，iterable2，fillval):** 这个迭代器按顺序交替打印 iterable 的值。如果其中一个 iterables 已完全打印，剩余的值将由分配给 fillvalue 的值填充。
    T3】例:

## 蟒蛇 3

```
# Python code to demonstrate the working of 
# zip_longest()

import itertools

# using zip_longest() to combine two iterables.
print ("The combined values of iterables is  : ")
print (*(itertools.zip_longest('GesoGes', 'ekfrek', fillvalue ='_' )))
```

**输出:**

```
The combined values of iterables is  : 
('G', 'e') ('e', 'k') ('s', 'f') ('o', 'r') ('G', 'e') ('e', 'k') ('s', '_')
```