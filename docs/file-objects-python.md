# Python 中的文件对象

> 原文:[https://www.geeksforgeeks.org/file-objects-python/](https://www.geeksforgeeks.org/file-objects-python/)

文件对象允许我们使用、访问和操作所有用户可访问的文件。人们可以读写任何这样的文件。
当文件操作因输入/输出相关原因失败时，会引发异常 IOError。这包括由于某种原因未定义操作的情况，如在 tty 设备上查找()或写入打开以供读取的文件。
文件有以下方法:

*   **open():** Opens a file in given access mode.

    ```py
     open(file_address, access_mode) 
    ```

    访问文件的示例:可以使用名为 open()的内置函数打开文件。这个函数接受文件的地址和 access_mode，并返回一个文件对象。
    有不同类型的访问 _ 模式:

    ```py
    r: Opens a file for reading only
    r+: Opens a file for both reading and writing
    w: Opens a file for writing only
    w+: Open a file for writing and reading.
    a: Opens a file for appending
    a+: Opens a file for both appending and reading
    ```

    当您在访问模式中添加“b”时，您可以以二进制格式而不是默认文本格式读取文件。当要访问的文件不是文本文件时使用。

*   **read([size])** :读取整个文件，并以字符串形式返回内容。从文件中最多读取大小字节(如果读取在获得大小字节之前达到 EOF，则读取较少)。如果大小参数为负或被忽略，则读取所有数据，直到达到 EOF。

    ```py
    # Reading a file
    f = open(__file__, 'r')

    #read()
    text = f.read(10)

    print(text)
    f.close()
    ```

*   **readline(【size】)**:读取文件的第一行，即在文件只有一行的情况下直到一个换行符或一个 e of，并返回一个字符串。如果 size 参数为非负数，则它是最大字节数(包括尾部换行符)，并且可能会返回一个不完整的行。仅当立即遇到电渗流时，才返回空字符串。

```py
# Reading a line in a file
f = open(__file__, 'r')

#readline()
text = f.readline(20)
print(text)
f.close()
```

*   **readline([sizehint])**:它逐行读取整个文件，并将每行更新为一个返回的列表。使用 readline()读取直到 EOF，并返回包含如此读取的行的列表。如果存在可选的 sizehint 参数，则不读取到 EOF，而是读取总计约为 sizehint 字节的整行(可能在舍入到内部缓冲区大小后)。

    ```py
    # Reading a file
    f = open(__file__, 'r')

    #readline()
    text = f.readlines(25)
    print(text)
    f.close()
    ```

    *   **write(string)**: It writes the contents of string to the file. It has no return value. Due to buffering, the string may not actually show up in the file until the flush() or close() method is called.

    ```py
    # Writing a file
    f = open(__file__, 'w')
    line = 'Welcome Geeks\n'

    #write()
    f.write(line)
    f.close()
    ```

    **不同模式下的更多示例:**

    ```py
    # Reading and Writing a file
    f = open(__file__, 'r+')
    lines = f.read()
    f.write(lines)
    f.close()
    ```

    ```py
    # Writing and Reading a file
    f = open(__file__, 'w+')
    lines = f.read()
    f.write(lines)
    f.close()
    ```

    ```py
    # Appending a file
    f = open(__file__, 'a')
    lines = 'Welcome Geeks\n'
    f.write(lines)
    f.close()
    ```

    ```py
    # Appending and reading a file
    f = open(__file__, 'a+')
    lines = f.read()
    f.write(lines)
    f.close()
    ```

    *   **writeline(sequence)**:它是文件的字符串序列，通常是字符串或任何其他可迭代数据类型的列表。它没有返回值。

    ```py
    # Writing a file
    f = open(__file__, 'a+')
    lines = f.readlines()

    #writelines()
    f.writelines(lines)
    f.close()
    ```

    *   **tell()** :返回一个整数，以字节

    ```py
    # Telling the file object position
    f = open(__file__, 'r')
    lines = f.read(10)

    #tell()
    print(f.tell())
    f.close()
    ```

    的形式告诉我们文件对象从文件开始的位置*   **seek(offset，from_where)** :用于改变文件对象的位置。偏移量表示要移动的字节数。from_where 指示字节将从何处移动。

    ```py
    # Setting the file object position
    f = open(__file__, 'r')
    lines = f.read(10)
    print(lines)

    #seek()
    print(f.seek(2,2))
    lines = f.read(10)
    print(lines)
    f.close()
    ```

    *   **刷新()**:刷新内部缓冲区，就像 stdio 的 fflush()。它没有返回值。close()会自动刷新数据，但如果您想在关闭文件之前刷新数据，则可以使用此方法。

    ```py
    # Clearing the internal buffer before closing the file
    f = open(__file__, 'r')
    lines = f.read(10)

    #flush()
    f.flush()
    print(f.read())
    f.close()
    ```

    *   **fileno()** :返回整数文件描述符，底层实现使用该描述符向操作系统请求 I/O 操作。

    ```py
    # Getting the integer file descriptor
    f = open(__file__, 'r')

    #fileno()
    print(f.fileno())
    f.close()
    ```

    *   **isatty()** :如果文件连接到类似 tty 的设备，则返回 True，否则返回 False。

    ```py
    # Checks if file is connected to a tty(-like) device
    f = open(__file__, 'r')

    #isatty()
    print(f.isatty())
    f.close()
    ```

    *   **next()** :当文件被用作迭代器时使用。方法被重复调用。此方法返回下一个输入行，或者在文件打开进行读取时在 EOF 处引发 StopIteration(打开进行写入时行为未定义)。

    ```py
    # Iterates over the file
    f = open(__file__, 'r')

    #next()
    try:
        while f.next():
            print(f.next())
    except:
        f.close()
    ```

    *   **截断([大小])** :截断文件的大小。如果存在可选的大小参数，文件将被截断到(最多)该大小。大小默认为当前位置。当前文件位置不变。请注意，如果指定的大小超过文件的当前大小，则结果取决于平台:可能包括文件可能保持不变，增加到指定的大小，就像零填充一样，或者增加到具有未定义新内容的指定大小。

    ```py
    # Truncates the file
    f = open(__file__, 'w')

    #truncate()
    f.truncate(10)
    f.close()
    ```

    *   **关闭()**:用于关闭打开的文件。关闭的文件不能再被读取或写入。

    ```py
    # Opening and closing a file
    f = open(__file__, 'r')

    #close()
    f.close()
    ```

    *   **属性**:
    *   **closed** :返回一个布尔值，表示文件对象的当前状态。如果文件关闭，则返回 true 如果文件打开，则返回 false。
    *   **编码**:该文件使用的编码。当 Unicode 字符串写入文件时，它们将使用这种编码转换为字节字符串。
    *   **模式**:文件的输入输出模式。如果文件是使用 open()内置函数创建的，这将是 mode 参数的值。
    *   **名称**:如果文件对象是使用 open()创建的，则为文件的名称。
    *   **换行符**:以通用换行符模式打开的文件对象具有反映文件中使用的换行符约定的属性。该属性的值为“\r”、“\n”、“\r\n”、无或包含所有新行类型的元组。
    *   **软空格**:这是一个布尔值，表示在使用 print 语句时，是否需要在另一个值之前打印一个空格字符。

        ```py
        f = open(__file__, 'a+')
        print(f.closed)
        print(f.encoding)
        print(f.mode)
        print(f.newlines)
        print(f.softspace)
        ```

**相关文章:**
[Python 文本文件读写](https://www.geeksforgeeks.org/reading-writing-text-files-python/)

**参考:**[【https://docs.python.org/2.4/lib/bltin-file-objects.html】](https://docs.python.org/2.4/lib/bltin-file-objects.html)
本文由**斯里·桑凯·乌帕拉帕蒂**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。