# Python 关键字和标识符

> 原文:[https://www . geesforgeks . org/python-关键字和标识符/](https://www.geeksforgeeks.org/python-keywords-and-identifiers/)

关键字是 python 中一些预定义的保留词，具有特殊的含义。关键字用于定义编码的语法。关键字不能用作标识符、函数和变量名。除了 True 和 False，python 中的所有关键字都是用小写写的。Python 3.7 中有 33 个关键词，让我们逐一浏览一下。

## **总 Python 关键词**

<figure class="table">

| 号码 | 关键词 | 描述 |
| --- | --- | --- |
| one | **和** | 这是一个逻辑运算符，如果两个操作数都为真，则返回真，否则返回假。 |
| Two | **或** | 这也是一个逻辑运算符，如果任何操作数为真，则返回真，否则返回假。 |
| three | **不是** | 这也是一个逻辑运算符，如果操作数为假，则返回真，否则返回假。 |
| four | **如果** | 这是用来做条件语句的。 |
| five | elif | Elif 是与 if 语句一起使用的条件语句。如果前面的条件不成立，则执行 elif 语句 |
| six | **否则** | Else 与 if 和 elif 条件语句一起使用。如果给定条件不为真，则执行 else 块。 |
| seven | **为** | 这是为循环创建的。 |
| eight | **而** | 此关键字用于创建 while 循环。 |
| nine | **断开** | 这用于终止循环。 |
| Ten | **为** | 这用于创建一个替代方案。 |
| Eleven | **def** | 它帮助我们定义函数。 |
| Twelve | **λ** | 它用来定义匿名函数。 |
| Thirteen | **通过** | 这是一个空语句，意味着它什么也不会做。 |
| Fourteen | **返回** | 它将返回值并退出函数。 |
| Fifteen | **真** | 这是一个布尔值。 |
| Sixteen | **假** | 这也是一个布尔值。 |
| Seventeen | **试试** | 它做了一个除了尝试的声明。 |
| Eighteen | **同** | with 关键字用于简化异常处理。 |
| Nineteen | **断言** | 此函数用于调试目的。通常用于检查代码的正确性 |
| Twenty | **级** | 它帮助我们定义一个类。 |
| Twenty-one | **继续** | 它会继续循环的下一次迭代 |
| Twenty-two | 的 | 它删除对对象的引用。 |
| Twenty-three | **除了** | 与异常一起使用，当异常发生时怎么办 |
| Twenty-four | **最后** | Finally 与 exceptions 一起使用，这是一个无论是否有异常都将被执行的代码块。 |
| Twenty-five | **从**开始 | 该表单用于导入任何模块的特定部分。 |
| Twenty-six | **全局** | 这声明了一个全局变量。 |
| Twenty-seven | **导入** | 这用于导入模块。 |
| Twenty-eight | 中的 | 它用于检查列表、元组等中是否存在值。 |
| Twenty-nine | **是** | 这用于检查两个变量是否相等。 |
| Thirty | **无** | 这是一个特殊的常数，用于表示空值或避免。重要的是要记住，0，任何空容器(例如空列表)都不会计算为无 |
| Thirty-one | **非本地** | 它被声明为非局部变量。 |
| Thirty-two | **升起** | 这引发了一个异常 |
| Thirty-three | **产量** | 它结束一个函数并返回一个生成器。 |

</figure>

**标识符:**标识符是用于标识变量、函数、类、模块等的名称。标识符是字符数字和下划线的组合。标识符应以字符或下划线开头，然后使用数字。字符是 a-z 或 A-Z、下划线(_)和数字(0-9)。我们不应该使用特殊字符(#，@，$，%，！)在标识符中。

**有效标识符示例:**

1.  var1
2.  _var1
3.  _1_var
4.  var_1

**无效标识符示例**

1.  ！var1
2.  1var
3.  1_var
4.  var#1

**示例 1:** 和、或、非、真、假关键字的示例。

## 计算机编程语言

```py
print("example of True, False, and, or not keywords")

#  compare two operands using and operator
print(True and True)

# compare two operands using or operator
print(True or False)

# use of not operator
print(not False)
```

**输出:**

```py
example of True, False, and, or not keywords
True
True
True
```

**示例 2:** 休息示例，继续。

## 计算机编程语言

```py
# execute for loop
for i in range(1, 11):

    # print the value of i
    print(i)

    # check the value of i is less then 5
    # if i lessthen 5 then continue loop
    if i < 5: 
        continue

    # if i greater then 5 then break loop
    else: 
        break
```

**输出:**

```py
1
2
3
4
5
```

**示例 3:**for、in、if、elif 和 else 关键字的示例。

## 计算机编程语言

```py
# run for loop
for t in range(1, 5):
  # print one of t ==1
    if t == 1:
        print('One')
   # print two if t ==2
    elif t == 2:
        print('Two')
    else:
        print('else block execute')
```

**输出:**

```py
One
Two
else block execute
else block execute
```

**示例 4:**def、if 和 else 关键字的示例。

## 计算机编程语言

```py
# define GFG() function using def keyword
def GFG():
    i=20
    # check i is odd or not
    # using if and else keyword
    if(i % 2 == 0):
        print("given number is even")
    else:
        print("given number is odd")   

# call GFG() function   
GFG()
```

**输出:**

```py
given number is even
```

**例 5:** 例试，除，养。

## 计算机编程语言

```py
def fun(num):
    try:
        r = 1/num
    except:
        print('Exception raies')
        return
    return r

print(fun(10))
print(fun(0))
```

**输出:**

```py
0.1
Exception raies
None
```

**示例 6:**lambda 关键字的示例。

## 计算机编程语言

```py
# define a anonymous using lambda keyword
# this lambda function increment the value of b
a = lambda b: b+1

# run a for loop
for i in range(1, 6):
    print(a(i))
```

**输出:**

```py
2
3
4
5
6
```

**例 7:** 使用 return 关键字。

## 计算机编程语言

```py
# define a function
def fun():
  # declare a variable
    a = 5
    # return the value of a
    return a
# call fun method and store
# it's return value in a variable 
t = fun()
# print the value of t
print(t)
```

**输出:**

```py
5
```

**示例 8:** 使用 del 关键字。

## 计算机编程语言

```py
# create a list
l = ['a', 'b', 'c', 'd', 'e']

# print list before using del keyword
print(l)

del l[2]

# print list after using del keyword
print(l)
```

**输出:**

```py
['a', 'b', 'c', 'd', 'e']
['a', 'b', 'd', 'e']
```

**例 9** :使用全局关键字。

## 计算机编程语言

```py
# declare a variable
gvar = 10

# create a function
def fun1():
  # print the value of gvar
    print(gvar)

# declare fun2()
def fun2():
  # declare global value gvar
    global gvar
    gvar = 100

# call fun1()
fun1()

# call fun2()
fun2()
```

**输出:**

```py
10
```

**例 10:**yield 关键字的例子。

## 计算机编程语言

```py
def Generator():
    for i in range(6):
        yield i+1

t = Generator()
for i in t:
    print(i)
```

**输出:**

```py
1
2
3
4
5
6
```

**示例 10:**assert 关键字的示例。

## 蟒蛇 3

```py
def sumOfMoney(money):
    assert len(money) != 0,"List is empty."
    return sum(money)

money = []
print("sum of money:",sumOfMoney(money))
```

**输出:**

```py
AssertionError: List is empty.
```