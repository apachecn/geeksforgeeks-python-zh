# Python Lambda 函数

> 原文:[https://www . geesforgeks . org/python-lambda-anonymous-functions-filter-map-reduce/](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

Python Lambda 函数是匿名函数意味着函数没有名字。我们已经知道 *def* 关键字是用来定义 Python 中的一个普通函数的。类似地， *lambda* 关键字用于在 Python 中定义匿名函数。

**Python Lambda 函数语法:**

```py
lambda arguments: expression
```

*   此函数可以有任意数量的参数，但只能有一个表达式，该表达式将被计算并返回。
*   只要需要函数对象，就可以自由使用 lambda 函数。
*   您需要记住，lambda 函数在语法上仅限于单个表达式。
*   除了函数中的其他类型的表达式之外，它在特定的编程领域还有各种用途。

让我们看看这个例子，试着理解正常定义函数和λ函数之间的区别。这是一个返回给定值立方的程序:

### 示例:λ函数示例

## 蟒蛇 3

```py
# Python program to demonstrate
# lambda functions

string ='GeeksforGeeks'

# lambda returns a function object
print(lambda string : string)
```

**Output**

```py
<function <lambda> at 0x7f65e6bbce18>
```

在上面的例子中，lambda 不是由 print 函数调用的，而是简单地返回函数对象及其存储位置。

因此，要让打印首先打印字符串，我们需要调用 lambda，这样字符串就可以通过打印。

### 示例:

## 蟒蛇 3

```py
# Python program to demonstrate
# lambda functions

x ="GeeksforGeeks"

# lambda gets pass to print
(lambda x : print(x))(x)
```

**Output**

```py
GeeksforGeeks
```

## Lambda 函数和 def 定义函数的区别

让我们看看这个例子，试着理解一个普通的 def 定义函数和 lambda 函数之间的区别。这是一个返回给定值立方的程序:

## 计算机编程语言

```py
# Python code to illustrate cube of a number
# showing difference between def() and lambda().
def cube(y):
    return y*y*y

lambda_cube = lambda y: y*y*y

# using the normally
# defined function
print(cube(5))

# using the lambda function
print(lambda_cube(5))
```

**输出:**

```py
125
125
```

正如我们在上面的例子中看到的，cube()函数和 lambda_cube()函数的行为和预期的一样。让我们再分析一下上面的例子:

*   **不使用 Lambda:** 这里，两者都返回给定数字的立方。但是，在使用 def 时，我们需要定义一个名为 cube 的函数，并需要向它传递一个值。执行之后，我们还需要使用 *return* 关键字从调用函数的地方返回结果。
*   **使用 Lambda:** Lambda 定义不包含“return”语句，它始终包含一个返回的表达式。我们还可以将 lambda 定义放在任何期望函数的地方，而且我们根本不需要将它赋给变量。这就是 lambda 函数的简单性。

让我们看看一些更常用的 lambda 函数的例子。

### 示例 1:带列表理解的 Python Lambda 函数

在这个例子中，我们将使用 lambda 函数进行列表理解，使用 lambda 函数进行循环。我们将试着打印 10 人的表格。

## 蟒蛇 3

```py
tables = [lambda x=x: x*10 for x in range(1, 11)]

for table in tables:
    print(table())
```

**Output**

```py
10
20
30
40
50
60
70
80
90
100
```

### 示例 2:带有 if-else 的 Python Lambda 函数

## 蟒蛇 3

```py
# Example of lambda function using if-else
Max = lambda a, b : a if(a > b) else b

print(Max(1, 2))
```

**Output**

```py
2
```

### 示例 3:具有多条语句的 Python Lambda

Lambda 函数不允许多个语句，但是，我们可以创建两个 lambda 函数，然后调用另一个 lambda 函数作为第一个函数的参数。让我们尝试使用 lambda 找到第二个最大元素。

## 蟒蛇 3

```py
List = [[2,3,4],[1, 4, 16, 64],[3, 6, 9, 12]]

# Sort each sublist
sortList = lambda x: (sorted(i) for i in x)

# Get the second largest element
secondLargest = lambda x, f : [y[len(y)-2] for y in f(x)]
res = secondLargest(List, sortList)

print(res)
```

**Output**

```py
[3, 16, 9]
```

在上面的例子中，我们创建了一个 lambda 函数，对给定列表的每个子列表进行排序。然后这个列表作为参数传递给第二个 lambda 函数，该函数返回排序列表中的 n-2 个元素，其中 n 是子列表的长度。

Lambda 函数可以与内置函数一起使用，如 [filter()](https://www.geeksforgeeks.org/filter-in-python/) 、 [map()](https://www.geeksforgeeks.org/python-map-function/) 和 [reduce()](https://www.geeksforgeeks.org/reduce-in-python/) 。

## 使用带有过滤器的 lambda()函数()

Python 中的 filter()函数接受一个函数和一个列表作为参数。这提供了一种优雅的方法来过滤掉序列“sequence”的所有元素，对于该序列，函数返回 True。下面是一个从输入列表中返回奇数的小程序:

**例 1:**

## 计算机编程语言

```py
# Python code to illustrate
# filter() with lambda()
li = [5, 7, 22, 97, 54, 62, 77, 23, 73, 61]

final_list = list(filter(lambda x: (x%2 != 0) , li))
print(final_list)
```

**输出:**

```py
[5, 7, 97, 77, 23, 73, 61]
```

**例 2:**

## 蟒蛇 3

```py
# Python 3 code to people above 18 yrs
ages = [13, 90, 17, 59, 21, 60, 5]

adults = list(filter(lambda age: age>18, ages))

print(adults)
```

**输出:**

```py
[90, 59, 21, 60]
```

## **使用 lambda()函数和 map()**

Python 中的 map()函数接受一个函数和一个列表作为参数。使用 lambda 函数和一个列表调用该函数，并返回一个新列表，其中包含该函数为每个项目返回的所有 lambda 修改项。示例:

**例 1:**

## 计算机编程语言

```py
# Python code to illustrate
# map() with lambda()
# to get double of a list.
li = [5, 7, 22, 97, 54, 62, 77, 23, 73, 61]

final_list = list(map(lambda x: x*2, li))
print(final_list)
```

**输出:**

```py
[10, 14, 44, 194, 108, 124, 154, 46, 146, 122]
```

**例 2:**

## 蟒蛇 3

```py
# Python program to demonstrate
# use of lambda() function
# with map() function
animals = ['dog', 'cat', 'parrot', 'rabbit']

# here we intend to change all animal names
# to upper case and return the same
uppered_animals = list(map(lambda animal: str.upper(animal), animals))

print(uppered_animals)
```

**输出:**

```py
['DOG', 'CAT', 'PARROT', 'RABBIT']
```

## **使用带有 reduce()的 lambda()函数**

Python 中的 reduce()函数接受一个函数和一个列表作为参数。使用 lambda 函数和 iterable 调用该函数，并返回新的简化结果。这在可迭代的对上执行重复操作。reduce()功能属于 ***功能工具*** 模块。

**例 1:**

## 计算机编程语言

```py
# Python code to illustrate
# reduce() with lambda()
# to get sum of a list

from functools import reduce
li = [5, 8, 10, 20, 50, 100]
sum = reduce((lambda x, y: x + y), li)
print (sum)
```

**输出:**

```py
193
```

这里，前两个元素的结果被添加到下一个元素中，这样一直持续到列表的末尾，如((((5+8)+10)+20)+50)+100)。

**例 2:**

## 蟒蛇 3

```py
# python code to demonstrate working of reduce()
# with a lambda function

# importing functools for reduce()
import functools

# initializing list
lis = [ 1 , 3, 5, 6, 2, ]

# using reduce to compute maximum element from list
print ("The maximum element of the list is : ",end="")
print (functools.reduce(lambda a,b : a if a > b else b,lis))
```

**输出:**

```py
The maximum element of the list is : 6
```

本文由**钦莫伊·蕾恩卡**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。