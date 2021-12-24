# Python 中可变与不可变对象

> 原文:[https://www . geesforgeks . org/mutable-vs-不可变对象-in-python/](https://www.geeksforgeeks.org/mutable-vs-immutable-objects-in-python/)

python 中的每个变量都保存一个对象的实例。python 中有两种类型的对象，即**可变的**和**不可变的对象**。每当一个对象被实例化时，它被分配一个唯一的对象 id。对象的类型是在运行时定义的，以后不能更改。但是，如果它是一个可变对象，它的状态可以改变。

总而言之，可变对象可以改变它们的状态或内容，而不可变对象不能改变它们的状态或内容。

*   **Immutable Objects :** These are of in-built types like **int, float, bool, string, unicode, tuple**. In simple words, an immutable object can’t be changed after it is created.

    ```py
    # Python code to test that 
    # tuples are immutable 

    tuple1 = (0, 1, 2, 3) 
    tuple1[0] = 4
    print(tuple1)
    ```

    错误:

    ```py
    Traceback (most recent call last):
      File "e0eaddff843a8695575daec34506f126.py", line 3, in 
        tuple1[0]=4
    TypeError: 'tuple' object does not support item assignment
    ```

    ```py
    # Python code to test that 
    # strings are immutable 

    message = "Welcome to GeeksforGeeks"
    message[0] = 'p'
    print(message)
    ```

    **错误:**

    ```py
    Traceback (most recent call last):
      File "/home/ff856d3c5411909530c4d328eeca165b.py", line 3, in 
        message[0] = 'p'
    TypeError: 'str' object does not support item assignment
    ```

*   **Mutable Objects :** These are of type **[list](https://www.geeksforgeeks.org/python-list/), [dict](https://www.geeksforgeeks.org/python-dictionary/), [set](https://www.geeksforgeeks.org/sets-in-python/)** . Custom classes are generally mutable.

    ```py
    # Python code to test that 
    # lists are mutable 
    color = ["red", "blue", "green"]
    print(color)

    color[0] = "pink"
    color[-1] = "orange"
    print(color)
    ```

    输出:

    ```py
    ['red', 'blue', 'green']
    ['pink', 'blue', 'orange']
    ```

**结论**

1.  python 中可变和不可变对象的处理方式不同。不可变对象的访问速度更快，更改**的成本也更高，因为这涉及到副本的创建。
    而易变的对象很容易改变。**
2.  当需要改变对象的大小或内容时，建议使用可变对象。
3.  **Exception :** However, there is an exception in immutability as well. We know that tuple in python is immutable. But the tuple consists of a sequence of names with unchangeable bindings to objects.
    Consider a tuple

    ```py
     tup = ([3, 4, 5], 'myname') 
    ```

    元组由一个字符串和一个列表组成。字符串是不可变的，所以我们不能改变它的值。但是列表的内容可以改变。**元组本身不是可变的，但是包含可变的项。**

根据经验，一般来说，类似原语的类型可能是不可变的，而定制的类似容器的类型大多是可变的。