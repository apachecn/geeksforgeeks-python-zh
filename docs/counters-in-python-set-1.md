# Python 中的计数器|集合 1(初始化和更新)

> 原文:[https://www.geeksforgeeks.org/counters-in-python-set-1/](https://www.geeksforgeeks.org/counters-in-python-set-1/)

**计数器**是包含在[系列](https://www.geeksforgeeks.org/python-collections-module/)模块中的**容器**。现在你们一定都在想什么是容器。先别急我们来讨论一下集装箱的问题。

## 什么是集装箱？

容器是保存对象的对象。它们提供了一种方法来访问包含的对象并迭代它们。内置容器的例子有元组、列表和字典。其他包含在[集合](https://www.geeksforgeeks.org/python-collections-module/)模块中。

计数器是字典的一个子类。因此，它是一个无序的集合，其中元素及其各自的计数作为字典存储。这相当于一个包或多套其他语言。

**语法:**

```py
class collections.Counter([iterable-or-mapping])
```

**初始化:**
计数器的构造函数可以通过以下任意一种方式调用:

*   带有项目序列*   带有包含键和计数的字典*   With keyword arguments mapping string names to counts

    **每种初始化类型的示例:**

    ```py
    # A Python program to show different ways to create
    # Counter
    from collections import Counter

    # With sequence of items 
    print(Counter(['B','B','A','B','C','A','B','B','A','C']))

    # with dictionary
    print(Counter({'A':3, 'B':5, 'C':2}))

    # with keyword arguments
    print(Counter(A=3, B=5, C=2))
    ```

    **所有三条线的输出相同:**

    ```py
    Counter({'B': 5, 'A': 3, 'C': 2})
    Counter({'B': 5, 'A': 3, 'C': 2})
    Counter({'B': 5, 'A': 3, 'C': 2})

    ```

    **更新:**
    我们也可以通过以下方式创建一个空的计数器:

    ```py
    coun = collections.Counter()

    ```

    并且可以通过 update()方法进行更新。语法相同:

    ```py
    coun.update(Data)

    ```

    ```py
    # A Python program to demonstrate update()
    from collections import Counter
    coun = Counter()

    coun.update([1, 2, 3, 1, 2, 1, 1, 2])
    print(coun)

    coun.update([1, 2, 4])
    print(coun)
    ```

    **输出:**

    ```py
    Counter({1: 4, 2: 3, 3: 1})
    Counter({1: 5, 2: 4, 3: 1, 4: 1})

    ```

    *   数据可以通过初始化中提到的三种方式中的任何一种来提供，计数器的数据将增加而不是替换。
    *   Counts can be zero and negative also.

        ```py
        # Python program to demonstrate that counts in 
        # Counter can be 0 and negative
        from collections import Counter

        c1 = Counter(A=4,  B=3, C=10)
        c2 = Counter(A=10, B=3, C=4)

        c1.subtract(c2)
        print(c1)
        ```

        **输出:**

        ```py
         Counter({'c': 6, 'B': 0, 'A': -6})
        ```

    *   We can use Counter to count distinct elements of a list or other collections.

        ```py
        # An example program where different list items are
        # counted using counter
        from collections import Counter

        # Create a list
        z = ['blue', 'red', 'blue', 'yellow', 'blue', 'red']

        # Count distinct elements and print Counter aboject
        print(Counter(z))
        ```

        **输出:**

        ```py
        Counter({'blue': 3, 'red': 2, 'yellow': 1})

        ```

本文由 **Mayank Rawat** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。