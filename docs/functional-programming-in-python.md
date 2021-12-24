# Python 中的函数编程

> 原文:[https://www . geesforgeks . org/functional-programming-in-python/](https://www.geeksforgeeks.org/functional-programming-in-python/)

函数式编程是一种编程范式，在这种范式中，我们试图以纯数学函数的方式绑定一切。这是一种声明式的编程风格。它的主要焦点是“**解决什么**”，而命令式风格的主要焦点是“**如何解决**”。它使用表达式而不是语句。表达式被求值以产生一个值，而语句被执行以分配变量。

## 函数式编程的概念

任何函数式编程语言都应该遵循这些概念。

*   **纯函数:**这些函数有两个主要性质。首先，它们总是为相同的参数产生相同的输出，而不考虑任何其他因素。其次，它们没有副作用，也就是说，它们确实修改了任何参数或全局变量，或者输出了一些东西。
*   **递归:**函数式语言中没有“for”或“while”循环。函数式语言中的迭代是通过递归实现的。
*   **函数是一级的，可以是高阶的:**一级函数作为一级变量处理。第一类变量可以作为参数传递给函数，可以从函数中返回或者存储在数据结构中。
*   **变量是不可变的:**在函数式编程中，我们不能在变量被初始化后修改它。我们可以创建新的变量，但不能修改现有的变量。

## Python 中的函数式编程

Python 也支持函数式编程范例，而不支持任何特殊功能或库。

#### 纯函数

如上所述，纯函数有两个性质。

*   它总是为相同的参数产生相同的输出。比如 3+7 无论如何总会是 10。
*   它不改变或修改输入变量。

第二个属性也称为不变性。纯函数的唯一结果是它返回的值。它们是决定性的。使用函数编程完成的程序很容易调试，因为纯函数没有副作用或隐藏的输入/输出。纯函数也使编写并行/并发应用程序变得更容易。当代码以这种风格编写时，智能编译器可以做很多事情——它可以并行处理指令，在需要时等待评估结果，并记住结果，因为只要输入不变，结果就不会改变。

**示例:**

```py
# Python program to demonstrate
# pure functions

# A pure function that does Not
# changes the input list and 
# returns the new List
def pure_func(List):

    New_List = []

    for i in List:
        New_List.append(i**2)

    return New_List

# Driver's code
Original_List = [1, 2, 3, 4]
Modified_List = pure_func(Original_List)

print("Original List:", Original_List)
print("Modified List:", Modified_List)
```

**输出:**

```py
Original List: [1, 2, 3, 4]
Modified List: [1, 4, 9, 16]

```

#### 递归

在函数编程中，没有`for`循环或`while`循环的概念，而是使用递归。递归是函数直接或间接调用自身的过程。在递归程序中，给出了基本情况的解，较大问题的解用较小的问题表示。可能会出现一个问题，什么是基本情况？基本情况可以被认为是告诉编译器或解释器退出函数的条件。

**注:**详见[递归](https://www.geeksforgeeks.org/recursion/)

**示例:**让我们考虑一个程序，它将在不使用任何 for 循环的情况下找到列表所有元素的总和。

```py
# Python program to demonstrate
# recursion

# Recursive Function to find
# sum of a list
def Sum(L, i, n, count):

    # Base case
    if n <= i:
        return count

    count += L[i]

    # Going into the recursion
    count = Sum(L, i + 1, n, count)

    return count

# Driver's code
L = [1, 2, 3, 4, 5]
count = 0
n = len(L)
print(Sum(L, 0, n, count))
```

**输出:**

```py
15

```

#### 函数是一级的，可以是高阶的

一级对象始终统一处理。它们可以存储在数据结构中，作为参数传递，或者用在控制结构中。如果一种编程语言将函数视为第一类对象，则称其支持第一类函数。

**一级函数的性质:**

*   函数是对象类型的一个实例。
*   您可以将函数存储在变量中。
*   您可以将函数作为参数传递给另一个函数。
*   您可以从函数返回函数。
*   您可以将它们存储在数据结构中，如哈希表、列表等

```py
# Python program to demonstrate
# higher order functions

def shout(text): 
    return text.upper() 

def whisper(text): 
    return text.lower() 

def greet(func): 
    # storing the function in a variable 
    greeting = func("Hi, I am created by a function passed as an argument.") 
    print(greeting)  

greet(shout) 
greet(whisper) 
```

**输出:**

```py
HI, I AM CREATED BY A FUNCTION PASSED AS AN ARGUMENT.
hi, I am created by a function passed as an argument.

```

**注意:**更多信息请参考 Python 中的[一级函数。](https://www.geeksforgeeks.org/first-class-functions-python/)

**内置高阶功能**

为了使列表和迭代器等可迭代对象的处理更加容易，Python 实现了一些常用的高阶函数。这些函数返回一个节省空间的迭代器。一些内置的高阶函数是:

*   **Map():** map() function returns a list of the results after applying the given function to each item of a given iterable (list, tuple etc.)

    > **语法:**地图(有趣，iter)
    > 
    > **参数:**
    > **乐趣:**这是一个函数，给定可迭代的每个元素都会传递到这个函数。
    > **iter:** 这是一个要映射的 iter。
    > 
    > **返回类型:**返回映射类的迭代器。

    **示例:**

    ```py
    # Python program to demonstrate working 
    # of map. 

    # Return double of n 
    def addition(n): 
        return n + n 

    # We double all numbers using map() 
    numbers = (1, 2, 3, 4) 
    results = map(addition, numbers) 

    # Does not Print the value
    print(results)

    # For Printing value
    for result in results:
        print(result, end = " ")
    ```

    **输出:**

    ```py
    <map object at 0x7fae3004b630>
    2 4 6 8 

    ```

    **注意:**更多信息请参考 [Python 地图()函数](http://geeksforgeeks.org/python-map-function/)

*   **filter():** The filter() method filters the given sequence with the help of a function that tests each element in the sequence to be true or not.

    > **语法:**过滤器(功能，序列)
    > 
    > **参数:**
    > **函数:**测试序列中每个元素是否为真的函数。
    > **序列:**需要过滤的序列，可以是集合、列表、元组，也可以是任意迭代器的容器。
    > 
    > **返回类型:**返回已经过滤的迭代器。

    **示例:**

    ```py
    # Python program to demonstrate working 
    # of the filter. 

    # function that filters vowels 
    def fun(variable): 

        letters = ['a', 'e', 'i', 'o', 'u'] 

        if (variable in letters): 
            return True
        else: 
            return False

    # sequence 
    sequence = ['g', 'e', 'e', 'j', 'k', 's', 'p', 'r'] 

    # using filter function 
    filtered = filter(fun, sequence) 

    print('The filtered letters are:') 

    for s in filtered: 
        print(s) 
    ```

    **输出:**

    ```py
    The filtered letters are:
    e
    e

    ```

    **注意:**更多信息请参考 Python 中的[过滤器()](https://www.geeksforgeeks.org/filter-in-python/)

*   **Lambda functions:** In Python, anonymous function means that a function is without a name. As we already know that def keyword is used to define the normal functions and the lambda keyword is used to create anonymous functions.

    **语法:**

    ```py
    lambda arguments: expression

    ```

    1)此函数可以有任意数量的参数，但只能有一个表达式，该表达式将被计算并返回。
    2)只要需要函数对象，就可以自由使用 lambda 函数。
    3)您需要记住，lambda 函数在语法上仅限于单个表达式。
    4)除了函数中的其他类型的表达式之外，它在特定的编程领域还有各种用途。

    **示例:**

    ```py
    # Python code to demonstrate
    # lambda

    cube = lambda x: x * x*x 
    print(cube(7)) 

    L = [1, 3, 2, 4, 5, 6]
    is_even = [x for x in L if x % 2 == 0]

    print(is_even)  
    ```

    **输出:**

    ```py
    343
    [2, 4, 6]

    ```

    **注意:**更多信息请参考 [Python lambda](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/) 。

#### 不变

不变性是一种可用于调试的函数式编程范例，因为它会在变量被更改的地方而不是值被更改的地方引发错误。Python 也支持一些不可变的数据类型，如字符串、元组、数字等。

**示例:**

```py
# Python program to demonstrate 
# immutable data types

# String data types
immutable = "GeeksforGeeks"

# changing the values will
# raise an error
immutable[1] = 'K'
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/ee8bf8d8f560b97c7ec0ef080a077879.py", line 10, in immutable[1] = 'K'
TypeError: 'str' object does not support item assignment 
```

## 函数式编程和面向对象编程的区别

当你对事物有一套固定的操作时，面向对象语言是很好的，随着代码的发展，你主要是添加新的东西。这可以通过添加实现现有方法的新类来实现，现有的类就不用管了。

当你有一套固定的东西时，函数式语言是好的，随着代码的发展，你主要是在现有的东西上添加新的操作。这可以通过添加用现有数据类型计算的新函数来实现，而现有的函数就不用管了。

| 功能程序设计 | 面向对象编程 |
| --- | --- |
| 这种编程范式强调函数的使用，其中每个函数执行特定的任务。 | 这种编程范式基于面向对象的概念。在创建对象实例的地方使用类 |
| 使用的基本元素是变量和函数。函数中的数据是不可变的(创建后不能更改)。 | 使用的基本元素是对象和方法，这里使用的数据是可变数据。 |
| 它遵循声明式编程模型。 | 它遵循命令式编程模型。 |
| 它使用递归进行迭代。 | 它使用循环进行迭代。 |
| 支持并行编程。 | 它不支持并行编程。 |
| 这个编程范例中的语句在执行时不需要遵循特定的顺序。 | 这种编程范式中的语句在执行时需要遵循一种顺序，即自下而上的方法。 |