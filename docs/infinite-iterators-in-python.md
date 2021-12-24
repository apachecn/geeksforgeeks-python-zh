# Python 中的无限迭代器

> 原文:[https://www.geeksforgeeks.org/infinite-iterators-in-python/](https://www.geeksforgeeks.org/infinite-iterators-in-python/)

[Python 中的迭代器](https://www.geeksforgeeks.org/iterators-in-python/)是可以与“`for in loop`”一起使用的任何 Python 类型。Python 列表、元组、字典和集合都是内置迭代器的例子。但是迭代器对象不必用尽，有时它可以是无限的。这种迭代器被称为**无限迭代器**。

Python 提供了三种类型的无限迭代器–

1.  **count(start, step):** This iterator **starts printing from the “start” number and prints infinitely**. If steps are mentioned, the numbers are skipped else step is 1 by default. See the below example for its use with `for in` loop.

    **示例:**

    ```
    # Python program to demonstrate
    # infinite iterators

    import itertools

    # for in loop
    for i in itertools.count(5, 5):
        if i == 35:
            break
        else:
            print(i, end =" ")
    ```

    **输出:**

    ```
    5 10 15 20 25 30

    ```

2.  **cycle(iterable):** This iterator prints all values in order from the passed container. It restarts **printing from beginning again when all elements are printed in a cyclic manner.**

    **示例#1:**

    ```
    # Python program to demonstrate
    # infinite iterators

    import itertools

    count = 0

    # for in loop
    for i in itertools.cycle('AB'):
        if count > 7:
            break
        else:
            print(i, end = " ")
            count += 1
    ```

    **输出:**

    ```
    A B A B A B A B 

    ```

    **示例#2:** 使用下一个函数。

    ```
    # Python program to demonstrate
    # infinite iterators

    import itertools

    l = ['Geeks', 'for', 'Geeks']

    # defining iterator
    iterators = itertools.cycle(l)

    # for in loop
    for i in range(6):

        # Using next function
        print(next(iterators), end = " ")
    ```

    **输出:**

    ```
    Geeks for Geeks Geeks for Geeks 

    ```

3.  **repeat(val, num):** This iterator repeatedly prints the passed value infinite number of times. If the optional keyword `num` is mentioned, then it repeatedly prints `num` number of times.

    **示例:**

    ```
    # Python code to demonstrate the working of  
    # repeat() 

    # importing "itertools" for iterator operations 
    import itertools 

    # using repeat() to repeatedly print number 
    print ("Printing the numbers repeatedly : ") 
    print (list(itertools.repeat(25, 4)))
    ```

    **输出:**

    ```
    Printing the numbers repeatedly : 
    [25, 25, 25, 25]

    ```