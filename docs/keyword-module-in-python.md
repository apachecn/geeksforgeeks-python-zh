# Python 中的关键字模块

> 原文:[https://www.geeksforgeeks.org/keyword-module-in-python/](https://www.geeksforgeeks.org/keyword-module-in-python/)

[Python](https://www.geeksforgeeks.org/python-programming-language/) 提供内置模块**关键字**，可以了解 Python 的保留关键字。

关键字模块允许您了解 Python 的保留字或关键字，并检查变量值是否是保留字。如果您不知道 Python 的所有关键字，您可以使用这个模块来检索这些信息。此外，它还可以帮助您通过在 Python shell 模式下使用其功能来检查一个单词是否是关键字。

**该模块的功能有:**

*   **keyword.iskeyword(parameter)**
    This function returns **True** if the parameter passed is a Python keyword else returns **False**. The parameter can be a string or a variable storing a string. It accordingly compares the parameter with Python keywords defined in the language and returns the output.

    **示例:**

    ```
    # Program to check whether a given
    # word is a Python keyword or not

    import keyword

    s ="if"
    t ="in"
    u ="GeeksforGeeks"

    # using iskeyword() function to check
    print(s, "is a keyword in Python:", 
          keyword.iskeyword(s))

    print("lambda is a keyword in Python:",
          keyword.iskeyword("lambda"))

    print("print is a keyword in Python:",
          keyword.iskeyword("print"))

    print(t, "is a keyword in Python:",
          keyword.iskeyword(t))

    print(u, "is a keyword in Python:", 
          keyword.iskeyword(u))
    ```

    **输出:**

    ```
    if is a keyword in Python: True
    lambda is a keyword in Python: True
    print is a keyword in Python: False
    in is a keyword in Python: True
    GeeksforGeeks is a keyword in Python: False
    ```

    从上面的例子可以看出，变量 **s** 和 **t** 的值是 Python 中的一个关键字，因此函数返回 **True** 。同样，字符串 **GeeksforGeeks** 不是关键字，因此函数返回 **False** 。

*   **keyword.kwlist**
    This is a predefined variable of keyword module that stores all the keywords of Python. Thus it can be used to display all the keywords of Python just by calling it.

    **示例:**

    ```
    # Program to display the list of Python keywords

    # importing keyword module
    import keyword

    # using keyword.kwlist to display the list of keywords

    print(keyword.kwlist)

    ```

    **输出:**

    > ['and '，' as '，' assert '，' break '，' class '，' continue '，' def '，' del '，' elif '，' else '，' except '，' exec '，' finally '，' for '，' from '，' global '，' if '，' import '，' in '，' is '，' lambda '，' not '，' or '，' pass '，'

    **注意:** keyword.kwlist 不是函数，因此不使用括号。kwlist 是之前在关键字模块中定义的变量。