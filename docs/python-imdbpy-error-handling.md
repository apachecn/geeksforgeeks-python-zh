# Python IMDbPY–错误处理

> 原文:[https://www.geeksforgeeks.org/python-imdbpy-error-handling/](https://www.geeksforgeeks.org/python-imdbpy-error-handling/)

在本文中，我们将看到如何处理与 Python 的 IMDb 模块相关的错误，与 IMDbPY 相关的错误(如无效搜索或数据库错误)可以通过检查 imdb 来捕获。IMDbErrorexception
为了处理错误，我们必须导入以下

```
from imdb import IMDbError
```

**语法:**

```
try :

    # code

except IMDbError as e:

    # action to handle it
```

如果出现任何与 IMDb 相关的错误，那么它将被除了 block 之外的程序捕获。
下面是实现。

## 蟒蛇 3

```
# importing libraries
from imdb import IMDb, IMDbError

# try block
try:

    # creating instance of imdb
    ia = IMDb()

    # getting person (it accept people id only)
    people = ia.get_person('abcd')

# except block  
except IMDbError as e:

    # printing the exception
    print(e)
```

**输出:**

```
invalid personID "abcd": invalid literal for int() with base 10: 'abcd'
```

另一个例子:在这个例子中，我们已经关闭了互联网连接

## 蟒蛇 3

```
# importing libraries
from imdb import IMDb, IMDbError

# try block
try:

    # creating instance of imdb
    ia = IMDb()

    # searching person
    people = ia.search_person('abcd')

# except block  
except IMDbError as e:

    # printing the exception
    print(e)
```

**输出:**

```
{'errcode': None, 'errmsg': 'None', 'url': 'https://www.imdb.com/find?q=abcd&s=nm', 'proxy': '', 'exception type': 'IOError', 'original exception': URLError(gaierror(11001, 'getaddrinfo failed'))}
```