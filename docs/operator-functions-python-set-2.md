# Python 中的运算符函数|集合 2

> 原文:[https://www . geesforgeks . org/operator-functions-python-set-2/](https://www.geeksforgeeks.org/operator-functions-python-set-2/)

[Python 中的运算符函数|集合 1](https://www.geeksforgeeks.org/operator-functions-in-python-set-1/)

本文将讨论更多的函数。

**1。setitem(ob，pos，val)** :-该功能用于**在集装箱中的某个**特定位置**分配**值。
操作–**ob[pos]= val**

**2。delitem(ob，pos)** :-该功能用于**删除容器中某个**特定位置**的值。
操作–**删除 ob【位置】****

**3。getitem(ob，pos)** :-该功能用于**获取容器中某个**特定位置**的值。
操作–**ob【pos】**** 

## 计算机编程语言

```
# Python code to demonstrate working of 
# setitem(), delitem() and getitem()

# importing operator module 
import operator

# Initializing list
li = [1, 5, 6, 7, 8]

# printing original list 
print ("The original list is : ",end="")
for i in range(0,len(li)):
    print (li[i],end=" ")

print ("\r")

# using setitem() to assign 3 at 4th position
operator.setitem(li,3,3)

# printing modified list after setitem()
print ("The modified list after setitem() is : ",end="")
for i in range(0,len(li)):
    print (li[i],end=" ")

print ("\r")

# using delitem() to delete value at 2nd index
operator.delitem(li,1)

# printing modified list after delitem()
print ("The modified list after delitem() is : ",end="")
for i in range(0,len(li)):
    print (li[i],end=" ")

print ("\r")

# using getitem() to access 4th element
print ("The 4th element of list is : ",end="")
print (operator.getitem(li,3))
```

输出:

```
The original list is : 1 5 6 7 8 
The modified list after setitem() is : 1 5 6 3 8 
The modified list after delitem() is : 1 6 3 8 
The 4th element of list is : 8
```

**4。setitem(ob，slice(a，b)，val)**:-该功能用于**设置容器中特定范围内的值**。
操作–**目标[a:b]= val**

**5。delitem(ob，slice(a，b))。
操作–**del obj【a:b】****

**6。getitem(ob，slice(a，b))。
操作–**obj【a:b】**T7】**

## 计算机编程语言

```
# Python code to demonstrate working of 
# setitem(), delitem() and getitem()

# importing operator module 
import operator

# Initializing list
li = [1, 5, 6, 7, 8]

# printing original list 
print ("The original list is : ",end="")
for i in range(0,len(li)):
    print (li[i],end=" ")

print ("\r")

# using setitem() to assign 2,3,4 at 2nd,3rd and 4th index
operator.setitem(li,slice(1,4),[2,3,4])

# printing modified list after setitem()
print ("The modified list after setitem() is : ",end="")
for i in range(0,len(li)):
    print (li[i],end=" ")

print ("\r")

# using delitem() to delete value at 3rd and 4th index
operator.delitem(li,slice(2,4))

# printing modified list after delitem()
print ("The modified list after delitem() is : ",end="")
for i in range(0,len(li)):
    print (li[i],end=" ")

print ("\r")

# using getitem() to access 1st and 2nd element
print ("The 1st and 2nd element of list is : ",end="")
print (operator.getitem(li,slice(0,2)))
```

输出:

```
The original list is : 1 5 6 7 8 
The modified list after setitem() is : 1 2 3 4 8 
The modified list after delitem() is : 1 2 8 
The 1st and 2nd element of list is : [1, 2]
```

**7。concat(ob1，obj2)** :此功能用于**连接**两个容器。
操作–**obj 1+obj 2**

**8。包含(ob1，obj2)** :-该功能用于**检查 obj1** 中是否存在 obj2。
操作–**obj 1 中的 obj 2**T7】

## 计算机编程语言

```
# Python code to demonstrate working of 
# concat() and contains()

# importing operator module 
import operator

# Initializing string 1
s1 = "geeksfor"

# Initializing string 2
s2 = "geeks"

# using concat() to concatenate two strings
print ("The concatenated string is : ",end="")
print (operator.concat(s1,s2))

# using contains() to check if s1 contains s2
if (operator.contains(s1,s2)):
       print ("geeksfor contains geeks")
else : print ("geeksfor does not contain geeks")
```

输出:

```
The concatenated string is : geeksforgeeks
geeksfor contains geeks
```

**9。和 _(a，b)** :-该函数用于计算上述参数的**位和**。
操作–**a&b**

**10。or_(a，b)** :-该函数用于计算上述参数的**位或**。
操作–**a | b**

**11 时。异或(a，b)** :-该函数用于计算上述参数的**位异或**。
操作–**a ^ b**

**12 时。反转(a)** :-该函数用于计算所述参数的**逐位反转**。
操作–**~ a**

## 蟒蛇 3

```
# Python code to demonstrate working of 
# and_(), or_(), xor(), invert()

# importing operator module 
import operator

# Initializing a and b

a = 1

b = 0

# using and_() to display bitwise and operation
print ("The bitwise and of a and b is : ",end="")
print (operator.and_(a,b))

# using or_() to display bitwise or operation
print ("The bitwise or of a and b is : ",end="")
print (operator.or_(a,b))

# using xor() to display bitwise exclusive or operation
print ("The bitwise xor of a and b is : ",end="")
print (operator.xor(a,b))

# using invert() to invert value of a
operator.invert(a)

# printing modified value
print ("The inverted value of a is : ",end="")
print (operator.invert(a))
```

**输出:**

```
The bitwise and of a and b is : 0
The bitwise or of a and b is : 1
The bitwise xor of a and b is : 1
The inverted value of a is : -2
```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。