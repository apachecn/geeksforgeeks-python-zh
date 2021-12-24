# python 中的 deque

> 原文:[https://www.geeksforgeeks.org/deque-in-python/](https://www.geeksforgeeks.org/deque-in-python/)

Python 中的 Deque(双端队列)是使用模块“**集合**实现的。在我们需要从容器两端进行更快的追加和弹出操作的情况下，dequee 优于[列表](https://www.geeksforgeeks.org/python-set-3-strings-lists-tuples-iterations/)，因为与提供 O(n)时间复杂度的列表相比，dequee 为追加和弹出操作提供了 **O(1)** 时间复杂度。

**示例:**

## 蟒蛇 3

```py
# Python code to demonstrate deque 

from collections import deque 

# Declaring deque 
queue = deque(['name','age','DOB'])  

print(queue)
```

**输出:**

```py
deque(['name', 'age', 'DOB'])
```

**我们来看看德格上的各种操作:**

*   **追加()** :-该函数用于**将参数中的**值插入到德格的**右端**。
*   **appendleft()** :-该函数用于**将参数中的**值插入到德格的**左端**。
*   **pop()** :-此功能用于**删除**一个来自德格**右端**的参数。
*   **popleft()** :-此功能用于**删除**一个来自德格**左端**的参数。

## 蟒蛇 3

```py
# Python code to demonstrate working of 
# append(), appendleft(), pop(), and popleft()

# importing "collections" for deque operations
import collections

# initializing deque
de = collections.deque([1,2,3])

# using append() to insert element at right end 
# inserts 4 at the end of deque
de.append(4)

# printing modified deque
print ("The deque after appending at right is : ")
print (de)

# using appendleft() to insert element at left end 
# inserts 6 at the beginning of deque
de.appendleft(6)

# printing modified deque
print ("The deque after appending at left is : ")
print (de)

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

**输出:**

```py
The deque after appending at right is : 
deque([1, 2, 3, 4])
The deque after appending at left is : 
deque([6, 1, 2, 3, 4])
The deque after deleting from right is : 
deque([6, 1, 2, 3])
The deque after deleting from left is : 
deque([1, 2, 3])
```

*   **索引(ele，beg，end)** :-此函数**返回参数中提到的值**的第一个索引，**从 beg 开始搜索直到结束**索引。
*   **插入(I，a)** :-此函数**在参数中指定的索引(i)** 处插入参数(a) **中提到的值**。
*   **移除()** :-此函数**移除参数中提到的第一个值**。
*   **count()** :-此函数**计算参数中提到的值的出现次数**。

## 蟒蛇 3

```py
# Python code to demonstrate working of 
# insert(), index(), remove(), count()

# importing "collections" for deque operations
import collections

# initializing deque
de = collections.deque([1, 2, 3, 3, 4, 2, 4])

# using index() to print the first occurrence of 4
print ("The number 4 first occurs at a position : ")
print (de.index(4,2,5))

# using insert() to insert the value 3 at 5th position
de.insert(4,3)

# printing modified deque
print ("The deque after inserting 3 at 5th position is : ")
print (de)

# using count() to count the occurrences of 3
print ("The count of 3 in deque is : ")
print (de.count(3))

# using remove() to remove the first occurrence of 3
de.remove(3)

# printing modified deque
print ("The deque after deleting first occurrence of 3 is : ")
print (de)
```

**输出:**

```py
The number 4 first occurs at a position : 
4
The deque after inserting 3 at 5th position is : 
deque([1, 2, 3, 3, 3, 4, 2, 4])
The count of 3 in deque is : 
3
The deque after deleting first occurrence of 3 is : 
deque([1, 2, 3, 3, 4, 2, 4])
```

*   **扩展(可迭代)** :-该功能用于**在德格右端**添加多个值。传递的参数是可迭代的。

*   **extendleft(iterable)** :-该功能用于**在德格左端**添加多个值。传递的参数是可迭代的。**由于左追加，顺序颠倒**。

*   **反转()** :-该功能用于**反转德格元素的**顺序。

*   **旋转()** :-此功能**按参数中指定的数量旋转德奎**。**如果指定的数字为负，则向左旋转。否则旋转向右。**

## 蟒蛇 3

```py
# Python code to demonstrate working of 
# extend(), extendleft(), rotate(), reverse()

# importing "collections" for deque operations
import collections

# initializing deque
de = collections.deque([1, 2, 3,])

# using extend() to add numbers to right end 
# adds 4,5,6 to right end
de.extend([4,5,6])

# printing modified deque
print ("The deque after extending deque at end is : ")
print (de)

# using extendleft() to add numbers to left end 
# adds 7,8,9 to right end
de.extendleft([7,8,9])

# printing modified deque
print ("The deque after extending deque at beginning is : ")
print (de)

# using rotate() to rotate the deque
# rotates by 3 to left
de.rotate(-3)

# printing modified deque
print ("The deque after rotating deque is : ")
print (de)

# using reverse() to reverse the deque
de.reverse()

# printing modified deque
print ("The deque after reversing deque is : ")
print (de)
```

**输出:**

```py
The deque after extending deque at end is : 
deque([1, 2, 3, 4, 5, 6])
The deque after extending deque at beginning is : 
deque([9, 8, 7, 1, 2, 3, 4, 5, 6])
The deque after rotating deque is : 
deque([1, 2, 3, 4, 5, 6, 9, 8, 7])
The deque after reversing deque is : 
deque([7, 8, 9, 6, 5, 4, 3, 2, 1]) 
```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。