# 封送—内部 Python 对象序列化

> 原文:[https://www . geesforgeks . org/marshal-internal-python-object-serialization/](https://www.geeksforgeeks.org/marshal-internal-python-object-serialization/)

序列化数据意味着将其转换为一个字节字符串，然后再从这个字符串中重建它。如果数据完全由基本的 Python 对象组成，序列化数据的最快方法是使用封送模块(对于用户定义的类， [Pickle](https://www.geeksforgeeks.org/pickle-python-object-serialization/) 应该是首选)。封送模块包含能够以二进制格式读写 Python 值的函数。

**封送**模块的存在主要是为了支持对的 Python 模块进行“伪编译”代码的读写。pyc 文件。该模块不支持所有 Python 对象类型。

支持以下类型:布尔值、整数、浮点数、复数、字符串、字节、字节数组、元组、列表、集合、frozen set、字典和代码对象，其中应该理解，元组、列表、集合、frozen set 和字典仅在其中包含的值本身被支持的情况下才被支持。单例无、省略号和停止迭代也可以被封送和解封。

**功能:**

1.  **marshal.version :**
    表示模块使用的格式。
    *   版本 0–历史格式
    *   版本 1–共享内部字符串
    *   版本 2–对浮点数使用二进制格式
    *   版本 3–支持对象实例化和递归
    *   版本 4–当前版本
2.  **marshal.dumps(value[, version]) :**
    The function returns the bytes object that would be written to a file by dump(value, file). The version argument indicates the data format that dumps should use. A ValueError exception is raised if the value has (or contains an object that has) an unsupported type.

    **例**T2】

    ## 蟒蛇 3

    ```
    # Python code to demonstrate serialization
    import marshal

    data = {12:'twelve', 'feep':list('ciao'), 1.23:4+5j, 
            (1,2,3):u'wer'}
    bytes = marshal.dumps(data)

    print (bytes)
    ```

    **输出**

    ```
    {tfeep[tctitatog®Gáz®ó?y@@ittwelve(iiiuwer0}

    ```

3.  **marshal.loads(bytes) :**
    This function can reconstruct the data by converting the bytes-like object to a value. EOFError, ValueError or TypeError is raised if no value is found.

    **例**T2】

    ## 蟒蛇 3

    ```
    # Python code to demonstrate de-serialization
    import marshal

    data = {12:'twelve', 'feep':list('ciao'), 1.23:4+5j, 
            (1,2,3):u'wer'}
    bytes = marshal.dumps(data)
    redata = marshal.loads(bytes)

    print (redata)
    ```

    **Output**

    ```
    {12: 'twelve', 1.23: (4+5j), 'feep': ['c', 'i', 'a', 'o'], (1, 2, 3): u'wer'}

    ```

4.  **marshal.dump(value，file[，version]) :**
    此函数用于在打开的可写二进制文件上写入支持的类型值。如果值的类型不受支持，则会引发值错误异常。
5.  **marshal.load(file) :**
    这个函数从打开的可读二进制文件中读取一个值并返回。如果未读取任何值，将引发 EOFError、ValueError 或 TypeError。

本文由**阿迪提·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。