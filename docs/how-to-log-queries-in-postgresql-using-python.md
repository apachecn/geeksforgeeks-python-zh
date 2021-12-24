# 如何使用 Python 在 PostgreSQL 中记录查询？

> 原文:[https://www . geesforgeks . org/how-log-query-in-PostgreSQL-using-python/](https://www.geeksforgeeks.org/how-to-log-queries-in-postgresql-using-python/)

Python 对 [PostgreSQL 有各种各样的数据库驱动。](https://www.geeksforgeeks.org/what-is-postgresql-introduction/)目前使用最多的版本是 psycopg2。它完全实现了 Python DB-API 2.0 规范。psycopg2 提供了许多有用的特性，如客户端和服务器端游标、异步通知和通信、复制命令支持等。

### 装置

安装 psycopg2 模块:

```
pip install psycopg2
```

为了记录关于命令的信息，我们需要安装 logtopg:

```
pip install logtopg
```

### 应用

*   情报收集
*   解决纷争
*   生成统计数据
*   审计
*   压型

### 日志记录级别及其目的

<figure class="table">

| **级** | **目的** |
| --- | --- |
| 调试 | 详细信息，通常仅在诊断问题时感兴趣。 |
| 信息 | 事情按预期进行的确认。 |
| 警告 | 表示发生了意想不到的事情，或表示在不久的将来会出现问题(例如“磁盘空间不足”)。软件仍按预期运行。 |
| 错误 | 由于一个更严重的问题，该软件无法执行某些功能。 |
| 批评的 | 严重错误，表示程序本身可能无法继续运行。 |

</figure>

所有记录器都是**根记录器**的后代。根记录器总是有一个显式的级别集，默认情况下是警告。根记录器可用于轻松打开和关闭所有库中的所有记录器。

### **记录器信息显示**

<figure class="table">

| **级** | **显示** |
| --- | --- |
| 调试 | 应该只出现在文件中 |
| 信息 | 应该出现在文件中 |
| 警告 | 应该出现在文件和标准输出中 |
| 错误 | 应该出现在文件和标准输出中 |
| 批评的 | 应该出现在文件和标准输出中 |

</figure>

为了更好地理解日志记录，这里有一个不连接 PostgreSQL 的简单代码，它只是在控制台中显示消息。

**示例:**

## 蟒蛇 3

```
import logging

# This will be printed only in file
logging.debug('This is a debug message')

# This will be printed only in file
logging.info('This is an info message')

logging.warning('This is a warning message')
logging.error('This is an error message')
logging.critical('This is a critical message')
```

**输出:**

![](img/10cbc71b594a8924e9f5e3d6a948bdd4.png)

使用了根记录器，只写了三条消息。这是因为默认情况下，只写入级别警告和更高的消息。

下面是另一个理解日志记录级别的例子。日志记录级别由 setLevel()设置。

**例 1:**

## 蟒蛇 3

```
import logging

# The getLogger() returns a logger with the specified name.
# If name is None, it returns the root logger.
logger = logging.getLogger('dev')

# Level is set
logger.setLevel(logging.DEBUG)

logger.debug('This is a debug message')
logger.info('This is an info message')
logger.warning('This is a warning message via setLevel')
logger.error('This is an error message via setLevel')
logger.critical('This is a critical message via setLevel')
```

**输出:**

![](img/12e3e336553a1156cf6107628b4d9927.png)

getLogger 和 setLevel

**例 2 :**

“mylib.py”应该位于“sample.py”所在的同一目录中，并且创建的文件“myapp.log”也将位于 mylib.py 和 sample.py 所在的同一目录中

**mylib.py**

## 蟒蛇 3

```
#Let this program name be mylib.py
import logging

def from_mylib():
    logging.info('I am from mylib')
```

让我们在另一个代码中使用 mylib.py

**样品 py**

## 蟒蛇 3

```
#logging module is required to log information
import logging

# User created python code and should be in same directory
import mylib

def main():

    # As we have specified myapp.log, all log information will be there
    # logging.INFO is the level, it will get printed
    logging.basicConfig(filename='myapp.log', level=logging.INFO)
    logging.info('Started to print logger info')

    # calling mylib method here as have imported. It should be
    # in same directory
    mylib.from_mylib()
    logging.info('Finished logging the information!!!')

# Main code
if __name__ == '__main__':
    main()
```