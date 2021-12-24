# Python | psycopg2-PostGreSQL 入门

> 原文:[https://www . geesforgeks . org/python-入门-psycopg2-postgresql/](https://www.geeksforgeeks.org/python-getting-started-with-psycopg2-postgresql/)

**PostgreSQL** 是一个功能强大的开源对象关系数据库系统。PostgreSQL 运行在所有主要的操作系统上。PostgreSQL 遵循 DataBase 系统的 ACID 属性，支持触发器、可更新视图和物化视图、外键。

为了连接 PostgreSQL，我们使用 **psycopg2** 。它是 python 语言中最好、最友好的数据库适配器。它对 Unicode 和 Python3 都很友好。

**需要安装–**

```py
 pip install psycopg2 
```

让我们开始部分了解 PostgreSQL 连接。

**Step #1: Connection to PostGreSQL**

```py
import psycopg2
conn = psycopg2.connect(database ="gfgdb", user = "gfguser",
                        password = "passgeeks", host = "52.33.0.1", 
                        port = "5432")

print("Connection Successful to PostgreSQL")
```

**第二步:申报光标**

允许 Python 代码在数据库会话中执行 PostgreSQL 命令。

```py
cur = conn.cursor()
```

**第三步:编写你的 SQL 查询并执行。**

```py
query = """select name, email from geeks_members;"""
cur.execute(query)
rows = cur.fetchall()

# Now 'rows' has all data
for x in rows:
    print(x[0], x[1])
```

**第四步:关闭连接**

```py
conn.close()
print('Connection closed')
```