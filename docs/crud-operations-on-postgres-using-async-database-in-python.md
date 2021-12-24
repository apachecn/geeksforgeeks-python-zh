# Python 中使用异步数据库对后缀进行 CRUD 操作

> 原文:[https://www . geesforgeks . org/crud-operations-on-postgres-using-async-database-in-python/](https://www.geeksforgeeks.org/crud-operations-on-postgres-using-async-database-in-python/)

CRUD 代表创建、读取、更新和删除操作。所有这些操作都可以使用异步数据库连接进行异步操作。在与 Postgres 数据库建立异步连接后，应用程序的性能显著提高，因为所有操作都是并发执行的，而不是按顺序执行的。python 中的异步数据库支持由数据库库提供。

**数据库:**

Databases 是一个 python 库，它为各种数据库提供 asyncio 支持，包括 PostgreSQL、MySQL 和 SQLite。对象关系映射器可以添加到这个数据库层来查询数据库。这种数据库支持也可以与任何异步网络框架集成，用于与数据库通信。

**安装数据库**:在终端运行以下 pip 命令。

```py
pip install databases

```

**安装 Postgresql 数据库驱动程序:**在终端运行以下 pip 命令。

```py
pip install databases[postgresql]

```

原油操作:

最初，在我们对数据库执行任何操作之前，连接到数据库并建立连接是很重要的。使用异步函数连接到数据库:
在数据库 URL 中，您必须用用户名、密码、主机和数据库替换您的数据库

## 蟒蛇 3

```py
from databases import Database
import asyncio

async def initalize_connection():
    database = Database('postgresql://username:password@host:5432/database')
    try:
        await database.connect()
        print('Connected to Database')
        await database.disconnect()
        print('Disconnecting from Database')
    except :
        print('Connection to Database Failed')

if __name__ == '__main__':
    asyncio.run(initalize_connection())
```

**输出:**

```py
Connected to Database 
Disconnecting from Database
```

**创建(C) :** 成功连接到数据库后，让我们使用:
创建一个名为**的表**

## 蟒蛇 3

```py
from databases import Database
import asyncio

async def create_table():

    database = Database('postgresql://username:password@host:5432/database')
    try:
        await database.connect()
        print('Connected to Database')

        # Create a table.
        query = """CREATE TABLE GfgExample (id INTEGER PRIMARY KEY, name VARCHAR(100))"""
        print('Created Table GfgExample Successfully')
        await database.execute(query=query)

        await database.disconnect()
        print('Disconnecting from Database')
    except :
        print('Connection to Database Failed')

if __name__=='__main__':
    asyncio.run(create_table())
```