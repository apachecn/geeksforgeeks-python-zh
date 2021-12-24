# 在 Python 中定义清理动作

> 原文:[https://www . geesforgeks . org/definition-clean-actions-python/](https://www.geeksforgeeks.org/defining-clean-actions-python/)

想一个你总是希望你的程序去做的任务，不管它是完美运行还是引发任何类型的错误。例如，我们使用 **try** 语句，该语句有一个可选子句–**“finally”**来执行清理操作，这些操作在任何情况下都必须执行。
**清理动作:**在离开 **try** 语句之前，**“finally”**子句总是被执行，不管是否引发异常。这些条款旨在定义在任何情况下都必须执行的清理行动。
当异常发生时，除条款外，不在**处理范围内，首先出现**最后出现**，然后错误默认为【代码 3】。**

**解释“定义清理动作”的 Python 程序**

**代码 1 :** 代码工作正常，最后进行清理动作

```py
# Python code to illustrate
# clean up actions
def divide(x, y):
    try:
        # Floor Division : Gives only Fractional Part as Answer
        result = x // y
    except ZeroDivisionError:
        print("Sorry ! You are dividing by zero ")
    else:
        print("Yeah ! Your answer is:", result)
    finally:
        print("I'm finally clause, always raised !! ")

# Look at parameters and note the working of Program
divide(3, 2)
```

**输出:**

```py
Yeah ! Your answer is : 1
I'm finally clause, always raised !! 

```

**代码 2 :** 代码引发错误，在**除了**条款中小心处理。请注意，清理操作将在最后进行。

```py
# Python code to illustrate
# clean up actions
def divide(x, y):
    try:
        # Floor Division : Gives only Fractional Part as Answer
        result = x // y
    except ZeroDivisionError:
        print("Sorry ! You are dividing by zero ")
    else:
        print("Yeah ! Your answer is:", result)
    finally:
        print("I'm finally clause, always raised !! ")

# Look at parameters and note the working of Program
divide(3, 0)
```

**输出:**

```py
Sorry ! You are dividing by zero 
I'm finally clause, always raised !!

```

**代码 3 :** 代码，引发错误但是我们除了子句没有任何**来处理。因此，首先采取清除动作，然后编译器引发**错误(默认情况下)**。**

```py
# Python code to illustrate
# clean up actions
def divide(x, y):
    try:
        # Floor Division : Gives only Fractional Part as Answer
        result = x // y
    except ZeroDivisionError:
        print("Sorry ! You are dividing by zero ")
    else:
        print("Yeah ! Your answer is:", result)
    finally:
        print("I'm finally clause, always raised !! ")

# Look at parameters and note the working of Program
divide(3, "3")
```

**输出:**

```py
I'm finally clause, always raised !! 
```

**错误:**

```py
Traceback (most recent call last):
  File "C:/Users/DELL/Desktop/Code.py", line 15, in 
    divide(3, "3")
  File "C:/Users/DELL/Desktop/Code.py", line 7, in divide
    result = x // y
TypeError: unsupported operand type(s) for //: 'int' and 'str'

```

本文由 <font color="green">**Mohit Gupta_OMG 供稿😀**</font> 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。