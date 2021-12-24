# 在 Python 3.9 中合并和更新字典操作符

> 原文:[https://www . geesforgeks . org/merging-and-update-dictionary-operators-in-python-3-9/](https://www.geeksforgeeks.org/merging-and-updating-dictionary-operators-in-python-3-9/)

Python 3.9 仍在开发中，计划于今年 10 月发布。2 月 26 日，开发团队已经发布了 alpha 4 版本。Python 3.9 的最新特性之一是合并和更新操作符。

通过使用 Python 中的各种函数和构造函数，有多种方法可以合并字典。在本文中，我们将查看所有执行这些操作的旧方法，以及 Python 开发团队发布的最新操作符，这肯定与所有 Python 程序员都有关系。

*   **Using method update():**

    Update()方法用于将第二个字典合并到第一个字典中，而不创建任何新字典和更新第一个字典的值，而第二个字典的值保持不变。此外，该函数不返回值。

    **示例:**

    ```py
    # Python code to merge dict 
    # using update() method 

    dict1 = {'a': 10, 'b': 5, 'c': 3} 
    dict2 = {'d': 6, 'c': 4, 'b': 8}

    # This return None 
    print("value returned by update function :", 
          dict1.update(dict2)) 

    # changes made in dict1 
    print("dict1 :", dict1)
    print("dict2 :", dict2)
    ```

    **Output:**

    ```py
    value returned by update function : None
    dict1 : {'a': 10, 'b': 8, 'c': 4, 'd': 6}
    dict2 : {'d': 6, 'c': 4, 'b': 8}

    ```

*   **Using ** in Python

    Python 中有一个技巧，我们可以使用单个表达式合并两个字典，并将其存储在第三个字典中。表情是**。这并不影响其他两本词典。**允许我们通过以键值对集合的形式扩展字典的内容，直接使用字典向函数传递多个参数。更多信息请参考 Python 中的[* * kwargs](https://www.geeksforgeeks.org/args-kwargs-python/)。在这个方法中，我们以顺序的方式将所有字典的所有元素传递到一个新字典中。随着字典内容一个接一个地传递，所有重复关键字的值都会被覆盖。

    **示例:**

    ```py
    # Python code to merge dict 
    # using a single expression 

    dict1 = {'a': 10, 'b': 5, 'c': 3}
    dict2 = {'d': 6, 'c': 4, 'b': 8}

    dict3 = {**dict1,**dict2} 

    print("dict1 :", dict1)
    print("dict2 :", dict2)
    print("dict3 :", dict3)
    ```

    **Output:**

    ```py
    dict1 : {'a': 10, 'b': 5, 'c': 3}
    dict2 : {'d': 6, 'c': 4, 'b': 8}
    dict3 : {'a': 10, 'b': 8, 'c': 4, 'd': 6}

    ```** 
*   ****Using | and |= operators

    字典并集`(|)`将返回一个由左操作数和右操作数合并而成的新字典，每个操作数必须是一个字典。如果一个键出现在两个操作数中，最后看到的值(即来自右边操作数的值)被选择。更新`(|=)`操作返回与右操作数合并的左操作数。

    **示例:**

    ```py
    # Python code to merge dict using 
    # (|) and (|=) operators  

    dict1 = {'a': 10, 'b': 5, 'c': 3} 
    dict2 = {'d': 6, 'c': 4, 'b': 8} 

    dict3 = dict1 | dict2
    print("Merging dict2 to dict1 (i.e., dict1|dict2) : ")
    print(dict3)

    dict4 = dict2 | dict1
    print("\nMerging dict1 to dict2 (i.e., dict2|dict1) : ")
    print(dict4)

    dict1 |= dict2
    print("\nMerging dict2 to dict1 and Updating dict1 : ")
    print("dict1 : " + dict1)
    print("dict2 : " + dict2)
    ```

    **Output:**

    ```py
    Merging dict2 to dict1 (i.e. dict1|dict2) : 
    {'a': 10, 'd': 6, 'c': 4, 'b': 8}

    Merging dict1 to dict2 (i.e. dict2|dict1) : 
    {'d': 6, 'a': 10, 'b': 5, 'c': 3}

    Merging dict2 to dict1 and Updating dict1 : 
    dict1 : {'a': 10, 'd': 6, 'c': 4, 'b': 8}
    dict2 : {'d': 6, 'c': 4, 'b': 8}

    ```****