# Python–捕捉所有异常

> 原文:[https://www.geeksforgeeks.org/python-catch-all-exceptions/](https://www.geeksforgeeks.org/python-catch-all-exceptions/)

在本文中，我们将讨论如何使用 try 捕获 Python 中的所有异常，除了借助适当示例的语句。但是在此之前，让我们看看 Python 中不同类型的错误。

Python 中一般有两类错误，即[语法错误和](https://www.geeksforgeeks.org/errors-and-exceptions-in-python/)异常。让我们看看它们之间的区别。

## 语法错误和异常的区别

**语法错误:**顾名思义，这个错误是由代码中错误的语法引起的。它导致程序的终止。

### 示例:Python 中的语法错误

## 蟒蛇 3

```py
# initialize the amount variable
amount = 10000

# check that You are eligible to
# purchase Dsa Self Paced or not
if(amount > 2999)
print("You are eligible to purchase Dsa Self Paced")
```

**输出:**

```py
SyntaxError: invalid syntax
```

**异常:**当程序语法正确，但代码导致错误时，会引发异常。这个错误不会停止程序的执行，但是，它会改变程序的正常流程。

### 示例:Python 中的异常

## 蟒蛇 3

```py
# initialize the amount variable
marks = 10000

# perform division with 0
a = marks / 0
print(a)
```

**输出:**

```py
ZeroDivisionError: division by zero
```

## 尝试和例外语句–捕获所有例外

[**【Try and except】语句**](https://www.geeksforgeeks.org/python-try-except/) 用于捕捉和处理 Python 中的异常。可以引发异常的语句保存在 try 子句中，处理异常的语句写在 except 子句中。

### 示例:Python 捕捉所有异常

## 蟒蛇 3

```py
# Python program to handle simple runtime error

a = [1, 2, 3]
try:
    print ("Second element = %d" %(a[1]))

    # Throws error since there are only 3 
    # elements in array
    print ("Fourth element = %d" %(a[3]))

except:
    print ("Error occurred")
```

**Output**

```py
Second element = 2
An error occurred
```

在上面的例子中，可能导致错误的语句被放在 try 语句中(在我们的例子中是第二个 print 语句)。第二个 print 语句试图访问列表中不存在的第四个元素，这将引发异常。然后，这个异常被 except 语句捕获。不指定任何类型的异常，try 块中导致的所有异常都将被 except 块捕获。我们还可以捕捉到一个特定的异常。让我们看看怎么做。

## 捕捉特定异常

try 语句可以有多个 except 子句，以便为不同的异常指定处理程序。请注意，最多将执行一个处理程序。例如，我们可以在上面的代码中添加 IndexError。添加特定异常的一般语法是–

```py
try:
   # statement(s)
except IndexError:
   # statement(s)
except ValueError:
   # statement(s)
```

### 示例:捕捉 Python 中的特定异常

## 蟒蛇 3

```py
# Program to handle multiple errors with one
# except statement
# Python 3

def fun(a):
    if a < 4:

        # throws ZeroDivisionError for a = 3
        b = a/(a-3)

    # throws NameError if a >= 4
    print("Value of b = ", b)

try:
    fun(3)
    fun(5)

# note that braces () are necessary here for
# multiple exceptions
except ZeroDivisionError:
    print("ZeroDivisionError Occurred and Handled")
except NameError:
    print("NameError Occurred and Handled")
```

**输出**

```py
ZeroDivisionError Occurred and Handled
```

如果你评论线趣(3)，输出会是

```py
NameError Occurred and Handled
```

上面的输出是这样的，因为一旦 python 试图访问 b 的值，就会出现 NameError。

**注意:**更多信息请参考我们的 [Python 异常处理教程](https://www.geeksforgeeks.org/python-exception-handling/)。