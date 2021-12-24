# 如何使用 Python 连接驻留在内存中的 SQLite 数据库？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 连接到驻留在内存中的 sqlite 数据库/](https://www.geeksforgeeks.org/how-to-connect-to-sqlite-database-that-resides-in-the-memory-using-python/)

在本文中，我们将学习如何使用 Python 将 SQLite 数据库连接连接到驻留在内存中的数据库。但是首先让我们简单介绍一下什么是 sqlite。

**SQLite** 是提供关系数据库管理系统的轻量级数据库软件库。一般来说，它是一个无服务器数据库，可以在几乎所有编程语言中使用，包括 Python。无服务器数据库意味着它不需要单独的服务器进程来运行。

下图显示了 SQLite 无服务器体系结构:

![](img/3c280c8d61c2b6f981e95cb75fabfd10.png)

映像 1.1 (SQLite 无服务器架构)

### 逐步实施

**第一步:导入 SQLite 模块**

要使用 Python 将 SQLite 数据库连接到驻留在内存中的数据库，首先我们将在编程中导入 SQLite，以便在程序中使用它的库。

在程序中导入 SQLite 的语法:

```py
import sqlite3
```

**步骤 2:创建连接**

在这一步中，我们将创建一个连接对象，它将把我们连接到数据库，并让我们执行 SQL 语句。为了创建一个连接对象，我们将使用 **connect()** 函数来创建一个连接对象。**连接()功能**在 SQLite 库中可用。

**语法:**

```py
conn = sqlite3.connect('gfgdatabase.db')   
```

它将创建一个名为“gfgdatabase.db”的数据库，并将创建一个名为“conn”的连接对象。下面是。形成的数据库文件:

![](img/f78c8c35d7710689715ea1d4f90c96f7.png)

图像 1.2(内存中的 gfg 数据库)

**第三步:在内存中创建数据库**

我们可以使用以下语法在内存中创建数据库。

```py
conn = sqlite3.connect(':memory:') 
```

它在内存中创建一个名为“gfgdatabase.db”的数据库。

**第 4 步:创建光标**

为了执行 SQLite 语句，我们需要一个游标对象。为了创建一个光标，我们将使用**光标()**方法。游标是连接对象的一种方法。为了执行 SQLite3 语句，我们应该首先建立一个连接，然后使用连接对象创建一个游标对象。

**语法:**

```py
cursor_object = connection.cursor()
```

**第五步:从 SQLite 导入错误**

如果在数据库创建和连接到内存时出现任何异常或运行时错误，那么就应该进行处理。为了处理这个问题，我们将从 SQLite 导入 Error。

语法:

```py
from sqlite3 import Error
```

**第 6 步:最后关闭连接**

一旦我们在步骤 2 中创建了与 SQLite 的连接，然后在步骤 3 中在 RAM 中创建了名为“gfgdatabase.db”的数据库，除此之外，直到步骤 5，我们已经完成了将 SQLite 数据库连接到驻留在内存中的数据库的所有过程。最后在这一步中，我们将关闭连接。为此，我们将使用 **close()** 功能。

**语法:**

```py
conn.close()
```

**以下是基于上述方法的完整程序:**

## 蟒蛇 3

```py
# import required modules
import sqlite3
from sqlite3 import Error as Err

# explicit function to connect  database
# that resides in the memory
def SQLite_connection():

    try:
        # connect to the database
        conn = sqlite3.connect('gfgdatabase.db')
        print("Database connection is established successfully!")

        # connect a database connection to the
        # database that resides in the memory
        conn = sqlite3.connect(':memory:')
        print("Established database connection to a database\
        that resides in the memory!")

    # if any interruption or error occurs
    except Err: print(Err)

    # terminate the connection   
    finally: conn.close()

# function call       
SQLite_connection()
```

**输出:**

![](img/d1b35ed13820eeb01aa4f6f044af9067.png)