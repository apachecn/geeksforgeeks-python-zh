# 最后 Python 中的关键词

> 原文:[https://www.geeksforgeeks.org/finally-keyword-in-python/](https://www.geeksforgeeks.org/finally-keyword-in-python/)

先决条件:[异常处理](https://www.geeksforgeeks.org/python-set-5-exception-handling/)、[尝试并除 Python 中的](https://www.geeksforgeeks.org/try-except-python/)

在编程中，可能会出现当前方法在处理一些异常时终止的情况。但是该方法在终止之前可能需要一些额外的步骤，比如关闭文件或网络等等。
所以，为了处理这些情况，Python 提供了一个关键字 **`finally`** ，总是在 [`try`和`except`](https://www.geeksforgeeks.org/try-except-python/) 块之后执行。 **`finally`** 块总是在*试块*正常终止后或试块因某种异常终止后执行。

**语法:**

```
try:
       # Some Code.... 

except:
       # optional block
       # Handling of exception (if required)

finally:
      # Some code .....(always executed)      

```

**要点–**

*   *最后*块总是在离开*尝试*语句后执行。如果某个异常不是由 except 块处理的，它将在 finally 块执行后重新引发。
*   *最后*块用于释放系统资源。
*   在*尝试*之后，可以不使用*而使用*最后使用*,除了*块，但在这种情况下不会处理任何异常。

**示例#1:**

```
# Python program to demonstrate finally

# No exception Exception raised in try block
try:
    k = 5//0 # raises divide by zero exception.
    print(k)

# handles zerodivision exception    
except ZeroDivisionError:   
    print("Can't divide by zero")

finally:
    # this block is always executed 
    # regardless of exception generation.
    print('This is always executed') 
```

**输出:**

```
Can't divide by zero
This is always executed
```

**例 2:**

```
# Python program to demonstrate finally

try:
    k = 5//1 # No exception raised
    print(k)

# intends to handle zerodivision exception    
except ZeroDivisionError:   
    print("Can't divide by zero")

finally:
    # this block is always executed 
    # regardless of exception generation.
    print('This is always executed') 
```

**输出:**

```
5
This is always executed

```

**例 3:**

```
# Python program to demonstrate finally

# Exception is not handled
try:
    k = 5//0 # exception raised
    print(k)

finally:
    # this block is always executed 
    # regardless of exception generation.
    print('This is always executed') 
```

**输出:**

```
This is always executed

```

**运行时错误–**

```
*Unhandled Exception* 
    k=5//0 #No exception raised
ZeroDivisionError: integer division or modulo by zero
```

**说明:**
在上面的代码中，异常是由*整数除法或以零为模*生成的，没有处理。执行*最后*块后，异常再次出现。这表明无论是否处理异常，最终都执行*块。*