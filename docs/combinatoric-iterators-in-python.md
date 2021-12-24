# Python 中的组合迭代器

> 原文:[https://www . geesforgeks . org/combinoric-iterators-in-python/](https://www.geeksforgeeks.org/combinatoric-iterators-in-python/)

迭代器是一个可以遍历其所有值的对象。简单地说，迭代器是可以循环的数据类型。生成器是迭代器，但是因为它们不能`[return](https://www.geeksforgeeks.org/python-return-statement/)` 值，所以它们在执行时会`[yield](https://www.geeksforgeeks.org/python-yield-keyword/)` 结果，使用“yield”函数。生成器可以像函数一样递归。这些用于简化组合结构(如排列、组合和笛卡尔乘积)的递归生成器被称为**组合迭代器**。

在 python 中，有 4 个组合迭代器:

1.  **Product()**

    该工具计算输入项的**笛卡尔乘积**。为了计算一个可迭代函数与其自身的乘积，我们使用可选的`repeat` 关键字参数来指定重复的次数。该功能的输出按排序顺序为`tuples` 。

    **语法:**

    ```py
    product(iterables*, repeat=1)
    ```

    **示例:**

    ```py
    # import the product function from itertools module
    from itertools import product

    print("The cartesian product using repeat:")
    print(list(product([1, 2], repeat=2)))
    print()

    print("The cartesian product of the containers:")
    print(list(product(['geeks', 'for', 'geeks'], '2')))
    print()

    print("The cartesian product of the containers:")
    print(list(product('AB', [3,4])))
    ```

    **输出:**

    ```py
    The cartesian product using repeat:
    [(1, 1), (1, 2), (2, 1), (2, 2)]

    The cartesian product of the containers:
    [('geeks', '2'), ('for', '2'), ('geeks', '2')]

    The cartesian product of the containers:
    [('A', 3), ('A', 4), ('B', 3), ('B', 4)]

    ```

2.  **Permutations()**

    `Permutations()`因为名字本身就能说明问题，所以它被用来生成一个可迭代的所有**可能的排列**。所有元素都是基于它们的位置而不是它们的价值被视为唯一的。该函数取一个可迭代的 group_size，如果 group_size 的值没有指定或者等于`None` ，那么 group_size 的值就变成了可迭代的长度。

    **语法:**

    ```py
    permutations(iterables*, group_size=None)
    ```

    **示例:**

    ```py
    # import the product function from itertools module
    from itertools import permutations

    print ("All the permutations of the given list is:") 
    print (list(permutations([1, 'geeks'], 2)))
    print()

    print ("All the permutations of the given string is:") 
    print (list(permutations('AB')))
    print()

    print ("All the permutations of the given container is:") 
    print(list(permutations(range(3), 2)))
    ```

    **输出:**

    ```py
    All the permutations of the given list is:
    [(1, 'geeks'), ('geeks', 1)]

    All the permutations of the given string is:
    [('A', 'B'), ('B', 'A')]

    All the permutations of the given container is:
    [(0, 1), (0, 2), (1, 0), (1, 2), (2, 0), (2, 1)]

    ```

3.  **Combinations():**

    这个迭代器打印**容器的所有可能的组合(没有替换)**，以指定的组大小按排序顺序传递参数。

    **语法:**

    ```py
    combinations(iterables*, group_size)
    ```

    **示例:**

    ```py
    # import combinations from itertools module

    from itertools import combinations

    print ("All the combination of list in sorted order(without replacement) is:") 
    print(list(combinations(['A', 2], 2)))
    print()

    print ("All the combination of string in sorted order(without replacement) is:")
    print(list(combinations('AB', 2)))
    print()

    print ("All the combination of list in sorted order(without replacement) is:")
    print(list(combinations(range(2),1)))
    ```

    **输出:**

    ```py
    All the combination of list in sorted order(without replacement) is:
    [('A', 2)]

    All the combination of string in sorted order(without replacement) is:
    [('A', 'B')]

    All the combination of list in sorted order(without replacement) is:
    [(0,), (1,)]

    ```

4.  **Combinations_with_replacement():**

    这个函数从 iterable 的元素中返回一个长度为 n 的子序列，其中 n 是函数用来确定函数生成的子序列长度的参数。单个元素**可以在具有替换功能的组合中重复自身**。

    **语法:**

    ```py
    combinations_with_replacement(iterables*, n=None)
    ```

    **示例:**

    ```py
    # import combinations from itertools module

    from itertools import combinations_with_replacement

    print ("All the combination of string in sorted order(with replacement) is:")
    print(list(combinations_with_replacement("AB", 2)))
    print()

    print ("All the combination of list in sorted order(with replacement) is:")
    print(list(combinations_with_replacement([1, 2], 2)))
    print()

    print ("All the combination of container in sorted order(with replacement) is:")
    print(list(combinations_with_replacement(range(2), 1)))
    ```

    **输出:**

    ```py
    All the combination of string in sorted order(with replacement) is:
    [('A', 'A'), ('A', 'B'), ('B', 'B')]

    All the combination of list in sorted order(with replacement) is:
    [(1, 1), (1, 2), (2, 2)]

    All the combination of container in sorted order(with replacement) is:
    [(0,), (1,)]

    ```