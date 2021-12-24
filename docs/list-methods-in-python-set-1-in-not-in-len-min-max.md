# 在 Python 中列出方法|集合 1 (in，not in，len()，min()，max()…)

> 原文:[https://www . geesforgeks . org/list-methods-in-python-set-1 in-not-in-len-min-max/](https://www.geeksforgeeks.org/list-methods-in-python-set-1-in-not-in-len-min-max/)

列表基础已经用 python 在下面的集合
[数据类型-列表、元组和迭代](https://www.geeksforgeeks.org/python-set-3-strings-lists-tuples-iterations/)中进行了介绍

本文将讨论列表方法。
**1。“in”运算符** :-该运算符用于**检查列表中是否存在某个元素**。如果列表中存在元素，则返回 true，否则返回 false。
**2。“不在”操作符** :-该操作符用于**检查列表中是否存在某个元素**。如果列表中没有元素，则返回 true，否则返回 false。

## 计算机编程语言

```
# Python code to demonstrate the working of
# "in" and "not in"
# initializing list
lis = [1, 4, 3, 2, 5]

# checking if 4 is in list using "in"
if 4 in lis:
        print ("List is having element with value 4")
else :  print ("List is not having element with value 4")

# checking if 4 is not list using "not in"
if 4 not in lis:
        print ("List is not having element with value 4")
else :  print ("List is having element with value 4")
```

**输出:**

```
List is having element with value 4
List is having element with value 4
```

**3。len()** :-该函数返回列表的**长度**。
**4。min()** :-该函数返回列表的**最小**元素。
**5。max()** :-该函数返回列表的**最大值**元素。

## 计算机编程语言

```
# Python code to demonstrate the working of
# len(), min() and max()
# initializing list 1
lis = [2, 1, 3, 5, 4]

# using len() to print length of list
print ("The length of list is : ", end="")
print (len(lis))

# using min() to print minimum element of list
print ("The minimum element of list is : ", end="")
print (min(lis))

# using max() to print maximum element of list
print ("The maximum element of list is : ", end="")
print (max(lis))
```

**输出:**

```
The length of list is : 5
The minimum element of list is : 1
The maximum element of list is : 5
```

**6。“+”运算符** :-该运算符用于**将两个列表连接成一个列表。
**7。“*”运算符** :-该运算符用于**将列表“n”乘以**，返回单个列表。**

## 计算机编程语言

```
# Python code to demonstrate the working of
# "+" and "*"
# initializing list 1
lis = [1, 2, 3]

# initializing list 2
lis1 = [4, 5, 6]

# using "+" to concatenate lists
lis2= lis + lis1

# printing concatenated lists
print ("list after concatenation is : ", end="")
for i in range(0,len(lis2)):
         print (lis2[i], end=" ")

print ("\r")

#using '*' to combine lists
lis3 = lis * 3

# printing combined lists
print ("list after combining is : ", end="")
for i in range(0,len(lis3)):
         print (lis3[i], end=" ")
```

**输出:**

```
list after concatenation is : 1 2 3 4 5 6 
list after combining is : 1 2 3 1 2 3 1 2 3 
```

**8。index(ele，beg，end)** :-该函数返回 beg 之后、end 之前第一次出现元素的**索引。
**9。count()** :-该功能统计列表中元素的**出现次数**。**

## 计算机编程语言

```
# Python code to demonstrate the working of
# index() and count()
# initializing list 1
lis = [2, 1, 3, 5, 4, 3]

# using index() to print first occurrence of 3
# prints 5
print ("The first occurrence of 3 after 3rd position is : ", end="")
print (lis.index(3, 3, 6))

# using count() to count number of occurrence of 3
print ("The number of occurrences of 3 is : ", end="")
print (lis.count(3))
```

**输出:**

```
The first occurrence of 3 after 3rd position is : 5
The number of occurrences of 3 is : 2
```

**相关文章:**
[Python 中的列表方法](https://www.geeksforgeeks.org/list-methods-python/)
[Python 中的列表方法| Set 2 (del，remove()，sort()，insert()，pop()，extend()……)](https://www.geeksforgeeks.org/list-methods-in-python-set-2-del-remove-sort-insert-pop-extend/)

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。