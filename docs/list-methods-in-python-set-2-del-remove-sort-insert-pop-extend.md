# Python 中的列表方法|集合 2 (del，remove()，sort()，insert()，pop()，extend()…)

> 原文:[https://www . geesforgeks . org/list-methods-in-python-set-2-del-remove-sort-insert-pop-extend/](https://www.geeksforgeeks.org/list-methods-in-python-set-2-del-remove-sort-insert-pop-extend/)

下面的第 1 集提到了一些列表方法

[在 Python 中列出方法|集合 1 (in，not in，len()，min()，max()…)](https://www.geeksforgeeks.org/list-methods-in-python-set-1-in-not-in-len-min-max/)

本文将讨论更多方法。

**1。del[a : b]** :-这个方法**从参数中提到的索引“a”到“b”删除范围**中的所有元素。

**2。pop()** :-此方法**删除其参数中提到的位置**处的元素**。**

```py
# Python code to demonstrate the working of
# del and pop()

# initializing list 
lis = [2, 1, 3, 5, 4, 3, 8]

# using del to delete elements from pos. 2 to 5
# deletes 3,5,4
del lis[2 : 5]

# displaying list after deleting 
print ("List elements after deleting are : ",end="")
for i in range(0, len(lis)):
    print(lis[i], end=" ")

print("\r")

# using pop() to delete element at pos 2
# deletes 3
lis.pop(2)

# displaying list after popping  
print ("List elements after popping are : ", end="")
for i in range(0, len(lis)):
    print(lis[i], end=" ")
```

输出:

```py
List elements after deleting are : 2 1 3 8 
List elements after popping are : 2 1 8 

```

**3。插入(a，x)** :-该函数**在其参数中提到的位置**插入一个元素。需要 2 个参数，**位置和元素被添加到各自的位置。**

**4。remove()** :-此函数用于**删除其参数中提到的数字的第一个出现的**。

```py
# Python code to demonstrate the working of
# insert() and remove()

# initializing list 
lis = [2, 1, 3, 5, 3, 8]

# using insert() to insert 4 at 3rd pos
lis.insert(3, 4)

# displaying list after inserting
print("List elements after inserting 4 are : ", end="")
for i in range(0, len(lis)):
    print(lis[i], end=" ")

print("\r")

# using remove() to remove first occurrence of 3
# removes 3 at pos 2
lis.remove(3)

# displaying list after removing 
print ("List elements after removing are : ", end="")
for i in range(0, len(lis)):
    print(lis[i], end=" ")
```

输出:

```py
List elements after inserting 4 are : 2 1 3 4 5 3 8 
List elements after removing are : 2 1 4 5 3 8 

```

**5。sort()** :-该功能**按照**递增顺序**对**列表进行排序。

**6。反向()** :-此功能**反向**列表的元素。

```py
# Python code to demonstrate the working of
# sort() and reverse()

# initializing list 
lis = [2, 1, 3, 5, 3, 8]

# using sort() to sort the list
lis.sort()

# displaying list after sorting
print ("List elements after sorting are : ", end="")
for i in range(0, len(lis)):
    print(lis[i], end=" ")

print("\r")

# using reverse() to reverse the list
lis.reverse()

# displaying list after reversing
print ("List elements after reversing are : ", end="")
for i in range(0, len(lis)):
    print(lis[i], end=" ")
```

输出:

```py
List elements after sorting are : 1 2 3 3 5 8 
List elements after reversing are : 8 5 3 3 2 1 

```

**7。扩展(b)** :-该功能用于**用**扩展存在于**另一列表**中的元素。该函数以**另一个列表作为参数**。

**8。clear()** :-该功能用于**清除列表的所有元素**。此操作后，列表变为空。

```py
# Python code to demonstrate the working of
# extend() and clear()

# initializing list 1
lis1 = [2, 1, 3, 5]

# initializing list 1
lis2 = [6, 4, 3]

# using extend() to add elements of lis2 in lis1
lis1.extend(lis2)

# displaying list after sorting
print ("List elements after extending are : ", end="")
for i in range(0, len(lis1)):
    print(lis1[i], end=" ")

print ("\r")

# using clear() to delete all lis1 contents
lis1.clear()

# displaying list after clearing
print ("List elements after clearing are : ", end="")
for i in range(0, len(lis1)):
    print(lis1[i], end=" ")
```

输出:

```py
List elements after extending are : 2 1 3 5 6 4 3 
List elements after clearing are : 

```

**相关文章:**
[Python 中的列表方法](https://www.geeksforgeeks.org/list-methods-python/)
[Python 中的列表方法|集合 1 (in，not in，len()，min()，max()……)](https://www.geeksforgeeks.org/list-methods-in-python-set-1-in-not-in-len-min-max/)

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。