# Python 中的迭代器函数|集合 2 (islice())、星图()、tee()..)

> 原文:[https://www . geesforgeks . org/iterator-functions-python-set-2 slice-star map-tee/](https://www.geeksforgeeks.org/iterator-functions-python-set-2islice-starmap-tee/)

[Python 中的迭代器函数|集合 1](https://www.geeksforgeeks.org/iterator-functions-in-python-set-1/)

**1。islice(可迭代、开始、停止、步骤)** :-这个迭代器**有选择地打印在其作为参数传递的可迭代容器**中提到的值。这个迭代器接受 **4 个参数，可迭代容器，起始位置。，结束位置和步骤。**

**2。星图。，元组列表)** :-这个迭代器以一个**函数和元组列表**为参数，根据函数从列表的每个元组中返回**值。**

```py
# Python code to demonstrate the working of 
# islice() and starmap()

# importing "itertools" for iterator operations
import itertools

# initializing list 
li = [2, 4, 5, 7, 8, 10, 20]

# initializing tuple list
li1 = [ (1, 10, 5), (8, 4, 1), (5, 4, 9), (11, 10 , 1) ]

# using islice() to slice the list acc. to need
# starts printing from 2nd index till 6th skipping 2
print ("The sliced list values are : ",end="")
print (list(itertools.islice(li,1, 6, 2)))

# using starmap() for selection value acc. to function
# selects min of all tuple values
print ("The values acc. to function are : ",end="")
print (list(itertools.starmap(min,li1)))
```

输出:

```py
The sliced list values are : [4, 7, 10]
The values acc. to function are : [1, 1, 4, 1]

```

**3。takewhile(func，iterable)** :-这个迭代器与 dropwhile()相反，它打印值**，直到函数第一次返回 false** 。

**4。tee(迭代器，计数)** :-这个迭代器**将容器拆分成参数中提到的多个迭代器**。

```py
# Python code to demonstrate the working of 
# takewhile() and tee()

# importing "itertools" for iterator operations
import itertools

# initializing list 
li = [2, 4, 6, 7, 8, 10, 20]

# storing list in iterator
iti = iter(li)

# using takewhile() to print values till condition is false.
print ("The list values till 1st false value are : ",end="")
print (list(itertools.takewhile(lambda x : x%2==0,li )))

# using tee() to make a list of iterators
# makes list of 3 iterators having same values.
it = itertools.tee(iti, 3)

# printing the values of iterators
print ("The iterators are : ")
for i in range (0,3):
    print (list(it[i]))
```

输出:

```py
The list values till 1st false value are : [2, 4, 6]
The iterators are : 
[2, 4, 6, 7, 8, 10, 20]
[2, 4, 6, 7, 8, 10, 20]
[2, 4, 6, 7, 8, 10, 20]

```

**5。zip _ long(iterable 1，iterable2，fillval。)** :-这个迭代器按顺序交替打印可迭代的**值**。如果其中一个项目被完全打印，则**剩余值由分配给 fillvalue** 的值填充。

```py
# Python code to demonstrate the working of 
# zip_longest()

# importing "itertools" for iterator operations
import itertools

# using zip_longest() to combine two iterables.
print ("The combined values of iterables is  : ")
print (*(itertools.zip_longest('GesoGes','ekfrek',fillvalue='_' )))
```

输出:

```py
The combined values of iterables is  : 
('G', 'e') ('e', 'k') ('s', 'f') ('o', 'r') ('G', 'e') ('e', 'k') ('s', '_')

```

**组合迭代器**

**1。product(iter1，iter2)** :-这个迭代器打印作为参数传递的两个可迭代容器的**笛卡尔乘积**。

**2。置换(iter，group_size)** :-这个迭代器打印可迭代的所有元素的所有**可能的置换**。每个置换组的**大小**是由 group_size 参数决定的**。**

```py
# Python code to demonstrate the working of 
# product() and permutations()

# importing "itertools" for iterator operations
import itertools

# using product() to print the cartesian product
print ("The cartesian product of the containers is : ")
print (list(itertools.product('AB','12')))

# using permutations to compute all possible permutations
print ("All the permutations of the given container is : ")
print (list(itertools.permutations('GfG',2)))
```

输出:

```py
The cartesian product of the containers is : 
[('A', '1'), ('A', '2'), ('B', '1'), ('B', '2')]
All the permutations of the given container is : 
[('G', 'f'), ('G', 'G'), ('f', 'G'), ('f', 'G'), ('G', 'G'), ('G', 'f')]

```

**3。组合(可迭代，group_size)** :-该迭代器按照**排序顺序打印**在**指定的组大小**中传递的容器的所有可能组合(不替换)**。**

**4。combinations _ with _ replacement(iterable，group_size)** :-这个迭代器按照**的排序顺序打印**指定的组大小**中传递的容器的所有可能组合(with replacement)** 。

```py
# Python code to demonstrate the working of 
# combination() and combination_with_replacement()

# importing "itertools" for iterator operations
import itertools

# using combinations() to print every combination
# (without replacement)
print ("All the combination of container in sorted order(without replacement) is : ")
print (list(itertools.combinations('1234',2)))

# using combinations_with_replacement() to print every combination
# with replacement
print ("All the combination of container in sorted order(with replacement) is : ")
print (list(itertools.combinations_with_replacement('GfG',2)))
```

输出:

```py
All the combination of container in sorted order(without replacement) is : 
[('1', '2'), ('1', '3'), ('1', '4'), ('2', '3'), ('2', '4'), ('3', '4')]
All the combination of container in sorted order(with replacement) is : 
[('G', 'G'), ('G', 'f'), ('G', 'G'), ('f', 'f'), ('f', 'G'), ('G', 'G')]

```

**无限迭代器**

**1。计数(开始，步骤)** :-这个迭代器**从“开始”号开始打印，无限打印**。如果提到步骤，则跳过这些数字，否则默认情况下步骤为 1。

示例:

```py
iterator.count(5,2) prints -- 5,7,9,11...infinitely

```

**2。cycle(iterable)** :-这个迭代器从传递的容器中按顺序打印所有的值。当所有元素以循环方式打印时，它会重新开始**打印。**

示例:

```py
iterator.cycle([1,2,3,4]) prints -- 1,2,3,4,1,2,3,4,1...infinitely

```

**3。repeat(val，num)** :-这个迭代器**重复打印**传递的值无限多次。如果 num。提到他们，直到那个数字。

```py
# Python code to demonstrate the working of 
# repeat()

# importing "itertools" for iterator operations
import itertools

# using repeat() to repeatedly print number
print ("Printing the numbers repeatedly : ")
print (list(itertools.repeat(25,4)))
```

输出:

```py
Printing the numbers repeatedly : 
[25, 25, 25, 25]

```

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。