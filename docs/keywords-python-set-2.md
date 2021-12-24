# Python 中的关键词|第二集

> 原文:[https://www.geeksforgeeks.org/keywords-python-set-2/](https://www.geeksforgeeks.org/keywords-python-set-2/)

Python 关键词–[简介](https://www.geeksforgeeks.org/check-string-valid-keyword-python/)
[Python 中的关键词|第 1 集](https://www.geeksforgeeks.org/keywords-python-set-1/)

**更多关键词:**
**16。试试**:这个关键字是用来异常处理的**，**是用来捕捉代码中使用关键字以外的错误。“尝试”块中的代码被检查，如果有任何类型的错误，除了块被执行。

**17。除了**:如上所述，这与“try”一起工作来捕捉异常。

**18。引发**:也用于异常处理，明确引发异常。

**19。最后**:不管“尝试”块的结果是什么，被称为“最后”的块总是被执行。详细文章–[Python 中的异常处理](https://www.geeksforgeeks.org/python-exception-handling/)

**20。对于**:这个关键字用于控制流量和循环。

**21。而**:有一个类似“for”的工作方式，用于控制流程和 for 循环。

**22。pass** :是 python 中的 null 语句。遇到这种情况时，什么也不会发生。这用于防止缩进错误，并用作占位符
详细文章–[传递](https://www.geeksforgeeks.org/loops-and-loop-control-statements-continue-break-and-pass-in-python/)

**23。导入**:此语句用于将特定模块包含到当前程序中。

**24。from** :一般用于导入，from 用于从导入的模块导入特定功能。

**25。as** :此关键字用于为导入的模块创建别名。即给导入的模块起一个新的名字。将数学作为我的数学导入。
详细条款–[进口，来自和作为](https://www.geeksforgeeks.org/python-modules/)

**26。lambda** :这个关键字用来进行内部不允许有语句的内联返回函数。详细文章–[地图，过滤器，λ](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)

**27。return** :此关键字用于从函数返回。详细文章–[Python 中的返回值](https://www.geeksforgeeks.org/g-fact-41-multiple-return-values-in-python/)。

**28。yield** :这个关键字和 return 语句一样使用，但是用来返回一个生成器。详细文章–[产出关键词](https://www.geeksforgeeks.org/use-yield-keyword-instead-return-keyword-python/)

**29。带**:这个关键字用来包装上下文管理器定义的方法内的代码块的执行。这个关键词在日常编程中使用不多。

**30。在**中:该关键字用于检查容器是否包含值。这个关键字也用于在容器中循环。

**31。is** :此关键字用于测试对象身份，即检查两个对象是否取相同的内存位置。

## 计算机编程语言

```py
# Python code to demonstrate working of
# in and is

# using "in" to check
if 's' in 'geeksforgeeks':
       print ("s is part of geeksforgeeks")
else : print ("s is not part of geeksforgeeks")

# using "in" to loop through
for i in 'geeksforgeeks':
    print (i,end=" ")

print ("\r")

# using is to check object identity
# string is immutable( cannot be changed once allocated)
# hence occupy same memory location
print (' ' is ' ')

# using is to check object identity
# dictionary is mutable( can be changed once allocated)
# hence occupy different memory location
print ({} is {})
```

**输出:**

```py
s is part of geeksforgeeks
g e e k s f o r g e e k s 
True
False
```

**32。全局**:这个关键字用来定义函数内部的一个变量是全局范围的。

**33。非局部**:这个关键字的工作原理类似于全局，但不是全局，这个关键字声明一个变量指向外部封闭函数的变量，如果是嵌套函数。

## 计算机编程语言

```py
# Python code to demonstrate working of
# global and non local

#initializing variable globally
a = 10

# used to read the variable
def read():
    print (a)

# changing the value of globally defined variable
def mod1():
    global a
    a = 5

# changing value of only local variable
def mod2():
    a = 15

# reading initial value of a
# prints 10
read()

# calling mod 1 function to modify value
# modifies value of global a to 5
mod1()

# reading modified value
# prints 5
read()

# calling mod 2 function to modify value
# modifies value of local a to 15, doesn't effect global value
mod2()

# reading modified value
# again prints 5
read()

# demonstrating non local
# inner loop changing the value of outer a
# prints 10
print ("Value of a using nonlocal is : ",end="")
def outer():
    a = 5
    def inner():
        nonlocal a
        a = 10
    inner()
    print (a)

outer()

# demonstrating without non local
# inner loop not changing the value of outer a
# prints 5
print ("Value of a without using nonlocal is : ",end="")
def outer():
    a = 5
    def inner():
        a = 10
    inner()
    print (a)

outer()
```

**输出:**

```py
10
5
5
Value of a using nonlocal is : 10
Value of a without using nonlocal is : 5
```

本文由 [**【曼吉特·辛格(S. Nandini)**](https://www.facebook.com/manjeet.04.singh) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。