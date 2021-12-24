# Python 中的上下文管理器

> 原文:[https://www.geeksforgeeks.org/context-manager-in-python/](https://www.geeksforgeeks.org/context-manager-in-python/)

**管理资源:**在任何编程语言中，像文件操作或数据库连接这样的资源使用都非常普遍。但是这些资源供应有限。因此，主要问题在于确保在使用后释放这些资源。如果它们没有被释放，那么它将导致资源泄漏，并可能导致系统变慢或崩溃。如果用户有一个自动设置和删除资源的机制，这将非常有帮助。在 Python 中，它可以通过使用上下文管理器来实现，这有助于正确处理资源。执行文件操作最常见的方式是使用带有关键字的*，如下所示:*

```
# Python program showing 
# a use of with keyword

with open("test.txt") as f:   
    data = f.read()
```

让我们以文件管理为例。当文件被打开时，文件描述符被消耗，这是一个有限的资源。一个进程一次只能打开一定数量的文件。下面的程序演示了它。

```
file_descriptors = []
for x in range(100000):
    file_descriptors.append(open('test.txt', 'w'))
```

**输出:**

```
Traceback (most recent call last):
  File "context.py", line 3, in 
OSError: [Errno 24] Too many open files: 'test.txt'

```

一条错误消息，指出打开了太多文件。上面的例子是一个文件描述符泄漏的例子。发生这种情况是因为打开的文件太多，并且没有关闭。程序员可能会忘记关闭打开的文件。

**使用上下文管理器管理资源:**

假设一个代码块引发了一个异常，或者如果它有一个带有多个返回路径的复杂算法，那么在所有地方关闭一个文件就会变得很麻烦。
一般在处理文件时使用其他语言*try-exception-final*y 用于确保文件资源在使用后关闭，即使出现异常。Python 提供了一种管理资源的简单方法:*上下文管理器*。使用带有关键字的*。当它被评估时，它应该产生一个执行上下文管理的对象。上下文管理器可以使用类或函数(使用装饰器)来编写。*

**创建上下文管理器:**

当使用类创建上下文管理器时，用户需要确保该类具有以下方法: *__enter__()* 和 *__exit__()* 。__enter__()返回需要管理的资源，__exit__()不返回任何内容，但执行清理操作。
首先，让我们创建一个名为 *ContextManager* 的简单类，以了解使用类创建上下文管理器的基本结构，如下所示:

```
# Python program creating a
# context manager

class ContextManager():
    def __init__(self):
        print('init method called')

    def __enter__(self):
        print('enter method called')
        return self

    def __exit__(self, exc_type, exc_value, exc_traceback):
        print('exit method called')

with ContextManager() as manager:
    print('with statement block')
```

**输出:**

```
init method called
enter method called
with statement block
exit method called

```

在这种情况下，会创建一个上下文管理器对象。这将作为关键字分配给*后面的变量，即*管理器*。运行上述程序时，将依次执行以下操作:*

*   __init__()

*   __ 输入 _ _()

*   语句体(带块的*内的代码)*

*   _ _ exit _ _()[此方法中的参数用于管理异常]

**使用上下文管理器的文件管理:**

让我们应用上面的概念来创建一个有助于文件资源管理的类。文件管理器类帮助打开一个文件，写/读内容，然后关闭它。

```
# Python program showing
# file management using 
# context manager

class FileManager():
    def __init__(self, filename, mode):
        self.filename = filename
        self.mode = mode
        self.file = None

    def __enter__(self):
        self.file = open(self.filename, self.mode)
        return self.file

    def __exit__(self, exc_type, exc_value, exc_traceback):
        self.file.close()

# loading a file 
with FileManager('test.txt', 'w') as f:
    f.write('Test')

print(f.closed)
```

**输出:**

```
True

```

**使用上下文管理器和语句进行文件管理:**

在用块执行*时，下列操作依次发生:*

*   执行 __init__ 方法时，将创建一个*文件管理器*对象，文件名为 *test.txt* ，模式为 *w* (写)。

*   __enter__ 方法以写入模式(设置操作)打开 *test.txt* 文件，并将*文件管理器*对象返回到变量 *f* 。

*   文本“测试”被写入文件。

*   __exit__ 方法负责在退出带有块的*时关闭文件(拆卸操作)。
    当*打印(关闭)*运行时，输出为*真*，因为*文件管理器*已经关闭了文件，否则需要明确关闭。*

**使用上下文管理器的数据库连接管理:**

让我们创建一个简单的数据库连接管理系统。一次可以打开的数据库连接数也是有限的(就像文件描述符一样)。因此，上下文管理器有助于管理与数据库的连接，因为程序员可能会忘记关闭连接。

```
# Python program shows the
# connection management 
# for MongoDB

from pymongo import MongoClient

class MongoDBConnectionManager():
    def __init__(self, hostname, port):
        self.hostname = hostname
        self.port = port
        self.connection = None

    def __enter__(self):
        self.connection = MongoClient(self.hostname, self.port)
        return self

    def __exit__(self, exc_type, exc_value, exc_traceback):
        self.connection.close()

# connecting with a localhost
with MongoDBConnectionManager('localhost', '27017') as mongo:
    collection = mongo.connection.SampleDb.test
    data = collection.find({'_id': 1})
    print(data.get('name'))
```

**使用上下文管理器和语句进行数据库连接管理:**

在用块执行*时，下列操作依次发生:*

*   执行 __init__ 方法时，创建一个 *MongoDBConnectionManager* 对象，主机名为*本地主机*，端口为 *27017* 。

*   __enter__ 方法打开 mongodb 连接并将 *MongoDBConnectionManager* 对象返回到变量 *mongo* 。

*   访问 SampleDb 数据库中的测试集合，检索 *_id* =1 的文档。打印文档的名称字段。

*   __exit__ 方法负责在退出带有块的*时关闭连接(拆卸操作)。*