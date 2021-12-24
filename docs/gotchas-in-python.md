# Python 中的陷阱

> 原文:[https://www.geeksforgeeks.org/gotchas-in-python/](https://www.geeksforgeeks.org/gotchas-in-python/)

[Python](https://www.geeksforgeeks.org/python-programming-language/) 对于大多数初入编程世界的人来说，是一门入门语言。这是因为它相当简单，需求量很大，而且最终功能强大。但是有些情况可能会迷惑或者欺骗新手程序员。这些被称为“陷阱”！源自非正式术语“抓住你了！”，gotcha 是一个案例或场景，当程序玩这个把戏，并导致一个与预期完全不同的输出。**需要注意的是，抓到你不是错误或异常**。这是一个完全有效的代码，导致不正确的输出，只是因为我们在编写程序时错过了一个微小的事实或点。因此，我们也可以认为 gotchas 是“编码时经常犯的错误”。

![python-gotchas](img/37c9e7c687fbd996f750a20ef4d94bd0.png)

让我们来看看 Python3 中一些最常见的陷阱以及如何解决它们:

***   括号有问题:**

当括号使用不正确或不必要时，会出现一些问题。

**示例:**

## 蟒蛇 3

```
# results in False
print(5>2 == True) 
```

**输出:**

```
False
```

这导致了 False，因为上面的表达式实际上意味着 5>2 且 2==True。这意味着，真与假。因此，最终结果是假的。
可以用括号纠正。

## 蟒蛇 3

```
# results in True
print((5>2) == True)
```

**输出:**

```
True

```

这里还有一个例子:

## 蟒蛇 3

```
# results in False
print(5 is (not None)) 
```

**输出:**

```
False
```

这是因为`"is not"`不同于单独使用的`"is"`和`"not"`。部分`(not None)`等于真，5 为真导致假。可以通过不使用任何括号来纠正。

## 蟒蛇 3

```
# results in True
print(5 is not None)
```

**输出:**

```
True

```

22.  **“is”, “==”, “is not”, “!=” : This is a short but very common gotcha. Many new programmers often think that `is` and `==` are the same thing. But it’s definitely not!

    ## 蟒蛇 3

    ```
    # results in True
    print(1 == True)

    # results in False
    print(1 is True) 
    ```

    **输出:**

    ```
    True
    False

    ```

    另一方面，`is not`和`!=`是一样的。

    ## 蟒蛇 3

    ```
    # results in True
    print(1 != False) 

    # results in True
    print(1 is not False)
    ```

    **输出:**

    ```
    True
    True

    ```** 
23.  ****Default arguments gotcha :

    在 Python 中，当函数第一次运行时，默认参数只声明一次，从那以后，每次都使用声明的参数。

    ## 蟒蛇 3

    ```
    def appendNew(appendTo =[]):      
        appendTo.append(1)   
        return appendTo

    # Driver's code
    print(appendNew())
    print(appendNew())
    ```

    预计每次我们调用`appendNew()`，都会创建一个新的列表，其中包含 1。但事实是这样的:

    ```
    [1]
    [1, 1]

    ```

    第二次运行函数时，不会再次创建变量`appendTo`。相反，它只是第一次创建，并被反复使用。我们可以通过以下方式解决这个问题:

    ## 蟒蛇 3

    ```
    def appendNew(appendTo = None):  
        if appendTo == None:
            appendTo =[]    
        appendTo.append(1)   
        return appendTo

    # Driver's code
    print(appendNew())
    print(appendNew())
    ```

    **输出:**

    ```
    [1]
    [1]

    ```**** 
24.  ******Scope gotchas :

    有时，我们必须记住我们正在处理的变量的范围，即它是全局范围(但在函数内部和外部都有效)还是局部范围(仅在函数内部有效)。

    **示例:**

    ## 蟒蛇 3

    ```
    list1 = [1, 2, 3]
    def baz1():

        # the code works fine
        list1.append(4) 
        return list1
    def baz2():

        # Doesn't work fine
        list1 += [5]      
        return list1

    # Driver's code
    print(baz1())
    print(baz2())
    ```

    **输出:**

    ```
    [1, 2, 3, 4]

    ```

    ```
    Traceback (most recent call last):
      File "/home/ba0dfa25407638b061076b45ce165ce5.py", line 15, in 
        print(baz2())
      File "/home/ba0dfa25407638b061076b45ce165ce5.py", line 10, in baz2
        list1 += [5]      
    UnboundLocalError: local variable 'list1' referenced before assignment

    ```

    发生这种情况是因为

    ```
    list1 += [5]
    ```

    意味着我们正在给变量`list1`赋值，但是 list1 定义在我们的函数范围之外。而在`baz1()`中，我们附加到列表 1，而不是赋值，因此它工作正常。****** 
25.  ******Variables are bound late in closures :

    Python 有一个臭名昭著的**后期绑定行为**。这里，我们指的是被迭代的变量的值在到达最后一次迭代时被最终确定为该值。让我们看一个例子:

    ## 蟒蛇 3

    ```
    def create_multipliers():

        # lambda function creates an iterable
        # list anonymously
        return [lambda c : i * c for i in range(6)] 

    for multiplier in create_multipliers():
        print multiplier(3)
    ```

    预期的结果当然是:

    ```
    0
    3
    6
    9
    12
    15

    ```

    但是我们得到的是:

    ```
    15
    15
    15
    15
    15
    15

    ```

    这是因为当循环迭代完成时，`i`的值为 5，因此每次 3*5 会得到 15。
    可以通过以下方式解决:

    ## 蟒蛇 3

    ```
    def create_multipliers():
        return [lambda x, i = i : i * x for i in range(6)]

    for multiplier in create_multipliers():
        print(multiplier(3))
    ```

    **输出:**

    ```
    0
    3
    6
    9
    12
    15

    ```****** 
26.  ******Mutating a list while iterating over it :

    这是新程序员几乎一直面临的最常见的问题。在处理一个列表或其他可变项时，如果我们在迭代它时对它进行变异，它肯定会导致错误。建议我们改为创建列表的副本，并对其进行变异，而不是原始列表。

    ## 蟒蛇 3

    ```
    # buggy program to print a list 
    # of odd numbers from 1 to 10

    even = lambda x : bool(x % 2)
    numbers = [n for n in range(10)]

    for i in range(len(numbers)):
        if not even(numbers[i]):
            del numbers[i]
    ```

    **输出:**

    ```
    Traceback (most recent call last):
      File "/home/92eed8bfd8c92fca3cf85f22e8cfd9ea.py", line 9, in 
        if not even(numbers[i]):
    IndexError: list index out of range

    ```

    但是如果我们用`numbers`的副本来代替:

    ## 蟒蛇 3

    ```
    # working program to print a 
    # list of odd numbers from 1 to 10

    even = lambda x : bool(x % 2)
    numbers = [n for n in range(10)]

    numbers[:] = [n for n in numbers if even(n)]
    print(numbers)  
    ```

    **输出:**

    ```
    [1, 3, 5, 7, 9]

    ```******