# Python 中的代码高尔夫

> 原文:[https://www.geeksforgeeks.org/code-golfing-in-python/](https://www.geeksforgeeks.org/code-golfing-in-python/)

**Python 中的 Code Golf** 指的是尝试使用尽可能少的字符来解决问题。就像在高尔夫球中，得分低的人获胜，最少数量的角色“获胜”。

[Python](https://www.geeksforgeeks.org/python-programming-language/) 由于向后兼容性、怪癖、它是一种高级语言以及所有的强制，是一种非常棒的代码高尔夫语言。因此，这里我们将看看 Python 语言中的一些代码高尔夫技巧。

## 使用循环

**折叠两个数字循环:**假设你正在迭代一个由 **m 行**和 **n 列**组成的矩阵。使用单个循环迭代 m*n 矩阵通常会更短，而不是两个嵌套的循环，一个用于行，一个用于列。

**原码:**

```py
m = n = 3
for i in range(m):
    for j in range(n):
        print(i, j)
```

**高尔夫代码:**

```py
m = n = 3
for i in range(m*n):
    print(i//n, i%n)
```

这项技术不仅限于两个嵌套循环，我们甚至可以为 **3 个或更多嵌套循环**编写相同的循环

```py
m, n, o = 2, 3, 4
for k in range(m*n*o):
    print(k//n//o, k%(n*o), k%o)
```

## 使用运算符

*   **加 1 或减 1:** 对于整数 n，可以写
    *   **-~n** 相当于 **n+1**
    *   **~-n** 相当于 **n-1**

这个工作原理是因为位翻转 **~x** 等于 **-x-1** 。这使用相同数量的字符，但可以间接切割空格或括号以获得运算符优先级。

*   **Membership in Set:** We write set in Python as S = {1, 2, 3, 4, 5}. To check whether an element e exists in Set S or not we can check the condition as **{e}&S** 

    **原码:**

```py
S = {1, 2, 3, 4, 5, 6, 7}
if 5 in S:
    print("Present")
else:
    print("Absent")
```

**高尔夫代码:**

```py
S = {1, 2, 3, 4, 5, 6, 7}
if {5}&S:
    print("Present")
else:
    print("Absent")
```

*   **Sibling of AND operator:** When we have two boolean or integer values, **a** and **b**, if we want to find out if both a and b are true, use ***** instead of **and**. 

    **原码:**

```py
if a and b:
    print("geeks")
else:
    print("geeksforgeeks")
```

**高尔夫代码:**

```py
if a*b:
    print("geeks")
else:
    print("geeksforgeeks")
```

*   **Sibling of OR operator:** When we have two boolean or integer values, **a** and **b**, if we want to find out if any one from a and b is true or both, use **|** instead of **or**. 

    **原码:**

```py
if a or b:
    print("geeks")
else:
    print("geeksforgeeks")
```

**高尔夫代码:**

```py
if a|b:
    print("geeks")
else:
    print("geeksforgeeks")
```

*   **Use += instead of append:** Instead of using append for adding one item to an existing list, we can use += operator. 

    **原码:**

```py
A.append(B)
```

**高尔夫代码:**

```py
A+=B,
```

**注意:B，**这里创建一个一元元组，可以像 A+=[B]中的[B]一样用来扩展 A。

*   **Use += instead of extend:** Instead of using extend for mergind one list into another at the end, we can use += operator. 

    **原码:**

```py
A.extend(B)
```

**高尔夫代码:**

```py
A+=B
```

*   **神奇的比较运算符:**我们面临很多情况，需要比较一个单个变量的不同值，一般我们通过不同的比较并结合**和**运算符来进行辩护。但是 Python 允许我们将所有的比较运算符放在一行中，而不使用**和**运算符。
    **原码:**

```py
if a>1 and a<10:
    print(a)
```

**高尔夫代码:**

```py
if 1<a<10:
    print(a)
```

**注意:**我们也可以同时对多个变量使用这个技巧。

**原码:**

```py
if a > 10 and b > 10 and 30 > a and 50 > b:
    print(a)
```

**高尔夫代码:**

```py
if 30 > a > 10 < b < 50:
    print(a)
```

## 使用函数

*   **Sibling of Floor function:** Suppose we want to find the floor value of a real number, we generally import floor function from math and then apply on the number. But we can simply apply the floor division with 1, which will give us a fruitful result. 

    **原码:**

```py
from math import floor
n = 3/2
print(floor(n))
```

**高尔夫代码:**

```py
n = 3/2
print(n//1)
```

*   **Sibling of Ceil function:** Suppose we want to find the ceil value of a real number, we generally import ceil function from math and then apply on the number. But we can do this operation in a more beautiful manner by first multiplying with -1 and then apply floor division with 1 and again multiply with -1. 

    **原码:**

```py
from math import ceil
n = 3/2
print(ceil(n))
```

**高尔夫代码:**

```py
n = 3/2
print(-(-n//1))
```

*   [**Lambda functions**](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/): Lambda definition does not include a “return” statement, it always contains an expression which is returned. We can also put a lambda definition anywhere a function is expected, and we don’t have to assign it to a variable at all. This is the simplicity of lambda functions. 

    **原码:**

```py
def c(a):
  if a < 3: return a-5
  else: return a+5
```

**高尔夫代码:**

```py
c=lambda a:a<3and a-5or a+5
```

*   **To get the entire alphabet string:** We can use the map function of python to get the string of whole alphabet set. 

    **原码:**

```py
string = 'abcdefghijklmnopqrstuvwxyz'
or 
string = [chr(i+97)for i in range(26)]
```

**高尔夫代码:**

```py
string = map(chr,range(97,123))
```

## 使用索引

*   **Indexing Technique for conditions:** When we have a certain condition which will give the answer in the form of small integers then we can use that in integer index in list or tuple to get our final answer. 

    **原码:**

```py
if a<b:return a
else:return b
```

**高尔夫代码:**

```py
return (b, a)[a<b]
```

*   **Reverse the Sequence:** We can reverse any list sequence using the good alien smiley face. 

    **原码:**

```py
string = 'geeksforgeeks'
for i in range(len(string)-1,-1,-1):
    print(string[i])
```

**高尔夫代码:**

```py
string = 'geeksforgeeks'
for i in string[::-1]:
    print(i)
```

*   **Use ~ to index from the back of a list:** If L is a list, use L[~i] to get the i’th element from the back. This is the i’th element of the reverse of L. The bit complement ~i equals -i-1, and so fixes the off-by-one error from L[-i]. 

    **原码:**

```py
string = 'geeksforgeeks'
for i in range(len(string)-1,-1,-1):
    print(string[i])
```

**高尔夫代码:**

```py
for i in range(len(string)):
    print(string[~i])
```

*   **Print the items of the list:** We can print the items of a list by using the ***** operator with the name of the list instead of looping through the list. 

    **原码:**

```py
A = [1,2,3,4,5,6,7]
for i in A:
    print(i,end = ' ')
```

**高尔夫代码:**

```py
A = [1,2,3,4,5,6,7]
print(*A) 
```

## 使用分配

*   **给多个变量赋值相同:**我们可以在一行或多行中给多个变量赋值相同的值。
    T3【原代码:

```py
# multiple lines
a = 0
b = 0
c = 0

# single line
a,b,c = 0,0,0
```

**高尔夫代码:**

```py
a = b = c = 0
```

*   **给变量分配相同或不同的字符:**我们可以在一行或多行中给多个变量分配相同或不同的字符。
    T3【原代码:

```py
# multiple lines
a = 'p'
b = 'q'
c = 'r'

# single line
a,b,c = 'p','q','r'
```

**高尔夫代码:**

```py
a,b,c = 'pqr'
```

## 使用转换

*   **Converting iterables into the list:** Imagine you have any ordered iterable like a tuple or string but you want to convert it into a list, so you can do this with ***** operator. 

    **原码:**

```py
a = (2,3,5,7,11)
x = list(a)

a = 'geeksforgeek'
x = list(a)
```

**高尔夫代码:**

```py
a = (2,3,5,7,11)
*x, = a

a = 'geeksforgeeks'
*x, = a
```

*   **Converting iterables into the Set:** Imagine you have any iterable like a list, tuple or string but you want to convert it into a Set, so you can do this with ***** operator. 

    **原码:**

```py
a = (2,3,5,7,11)
x = set(a)

a = [2,3,5,7,11]
x = set(a)

a = 'geeksforgeeks'
x = set(a)
```

**高尔夫代码:**

```py
a = (2,3,5,7,11)
x = {*a}

a = [2,3,5,7,11]
x = {*a}

a = 'geeksforgeeks'
x = {*a}
```

*   **Converting iterables into the Tuple:** Imagine you have any iterable like a list, set, or string but you want to convert it into a Tuple, so you can do this with ***** operator. 

    **原码:**

```py
a = (2,3,5,7,11)
x = tuple(a)

a = [2,3,5,7,11]
x = tuple(a)

a = 'geeksforgeeks'
x = tuple(a)
```

**高尔夫代码:**

```py
a = (2,3,5,7,11)
x = (*a,)

a = [2,3,5,7,11]
x = (*a,)

a = 'geeksforgeeks'
x = (*a,)
```

## 在不同材料的连接过程中

*   **Joining multiple Lists:** We can join the multiple lists using **+** operator, but for code golfing we can do the same using ***** operator. 

    **原码:**

```py
T = [2,3,4,5,6,7,8,9]
new_T = [1]+T+[10]
```

**高尔夫代码:**

```py
T = [2,3,4,5,6,7,8,9]
new_T = [1,*T,10]
```

*   **Joining multiple Lists:** We can join the multiple lists using **+** operator, but for code golfing we can do the same using ***** operator. 

    **原码:**

```py
T = (2,3,4,5,6,7,8,9)
new_T = (1,)+T+(10,)
```

**高尔夫代码:**

```py
T = (2,3,4,5,6,7,8,9)
new_T = (1,*T,10)
```