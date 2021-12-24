# PostgreSQL–连接到 Python 中的 PostgreSQL 数据库服务器

> 原文:[https://www . geesforgeks . org/PostgreSQL-connect-to-PostgreSQL-database-server-in-python/](https://www.geeksforgeeks.org/postgresql-connect-to-postgresql-database-server-in-python/)

**psycopg** 数据库适配器用于通过 python 连接 PostgreSQL 数据库服务器。

安装 psycopg:

首先，从终端使用以下命令行:

```py
pip install psycopg

```

如果您已经将源包下载到您的计算机中，您可以按照如下方式使用 setup . py:

```py
python setup.py build
sudo python setup.py install
```

### 创建新数据库

首先，使用任何客户端工具(如 pgAdmin 或 psql)登录 PostgreSQL 数据库服务器。

其次，使用以下语句在 PostgreSQL 数据库服务器中创建一个名为 suppliers 的新数据库。

```py
CREATE DATABASE suppliers;
```

### 使用 psycopg2 连接到 PostgreSQL 数据库

要连接到供应商数据库，可以使用 psycopg2 模块的 connect()函数。

connect()函数创建一个新的数据库会话，并返回连接类的一个新实例。通过使用连接对象，您可以创建一个新的游标来执行任何 SQL 语句。

要调用 connect()函数，需要将 PostgreSQL 数据库参数指定为连接字符串，并将其传递给如下函数:

```py
conn = psycopg2.connect("dbname=suppliers user=postgres password=postgres")
```

或者您可以使用关键字参数列表:

```py
conn = psycopg2.connect(
    host="localhost",
    database="suppliers",
    user="postgres",
    password="Abcd1234")
```

以下是连接参数列表:

数据库:要连接的数据库的名称。

用户:用于验证的用户名。

密码:用于验证的密码。

主机:数据库服务器地址，例如本地主机或 IP 地址。

端口:如果没有提供，默认为 5432 的端口号。

为了更方便，您可以使用配置文件来存储所有连接参数。

下面显示了 database.ini 文件的内容:

```py
[postgresql]
host=localhost
database=suppliers
user=postgres
password=SecurePas$1
```

通过使用 database.ini，您可以在将代码移动到生产环境时更改 PostgreSQL 连接参数，而无需修改代码。

请注意，如果使用 git，需要将 database.ini 添加到。gitignore 文件，以避免将敏感信息提交给像 github 这样的公共 repo。那个。gitignore 文件会是这样的:

```py
database.ini
```

下面的 config()函数读取 database.ini 文件并返回连接参数。config()函数放在 config.py 文件中:

```py
#!/usr/bin/python
from configparser import ConfigParser

def config(filename='database.ini', section='postgresql'):
    # create a parser
    parser = ConfigParser()
    # read config file
    parser.read(filename)

    # get section, default to postgresql
    db = {}
    if parser.has_section(section):
        params = parser.items(section)
        for param in params:
            db[param[0]] = param[1]
    else:
        raise Exception('Section {0} not found in the {1} file'.format(section, filename))

    return db
```

下面的 connect()函数连接到供应商数据库，并打印出 PostgreSQL 数据库版本。

```py
#!/usr/bin/python
import psycopg2
from config import config

def connect():
    """ Connect to the PostgreSQL database server """
    conn = None
    try:
        # read connection parameters
        params = config()

        # connect to the PostgreSQL server
        print('Connecting to the PostgreSQL database...')
        conn = psycopg2.connect(**params)

        # create a cursor
        cur = conn.cursor()

    # execute a statement
        print('PostgreSQL database version:')
        cur.execute('SELECT version()')

        # display the PostgreSQL database server version
        db_version = cur.fetchone()
        print(db_version)

    # close the communication with the PostgreSQL
        cur.close()
    except (Exception, psycopg2.DatabaseError) as error:
        print(error)
    finally:
        if conn is not None:
            conn.close()
            print('Database connection closed.')

if __name__ == '__main__':
    connect()
```

它是如何工作的。

首先，从 database.ini 文件中读取数据库连接参数。

接下来，通过调用 connect()函数创建一个新的数据库连接。

然后，创建一个新的游标并执行一条 SQL 语句来获得 PostgreSQL 数据库版本。

之后，通过调用 cursor 对象的 fetchone()方法读取结果集。

最后，通过调用游标和连接对象的 close()方法来关闭与数据库服务器的通信。

### 执行 connect.py 文件

要执行 connect.py 文件，可以使用以下命令:

```py
python connect.py
```

您将看到以下输出:

```py
Connecting to the PostgreSQL database...
PostgreSQL database version:
('PostgreSQL 12.3, compiled by Visual C++ build 1914, 64-bit', )
Database connection closed.
```

### 解决纷争

如果发生错误，connect()函数将引发数据库错误异常。要了解它是如何工作的，可以更改 database.ini 文件中的连接参数。

例如，如果您将主机更改为 localhosts，程序将输出以下消息:

```py
Connecting to the PostgreSQL database...
could not translate host name "localhosts" to address: Unknown host
```

当您将数据库更改为不存在的数据库时，以下内容会显示错误消息，例如供应商:

```py
Connecting to the PostgreSQL database...
FATAL: database "supplier" does not exist
```

如果您将用户更改为后进，将不会成功通过身份验证，如下所示:

```py
Connecting to the PostgreSQL database...
FATAL: password authentication failed for user "postgress"
```