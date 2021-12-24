# PostgreSQL–用 Python 创建表

> 原文:[https://www . geesforgeks . org/PostgreSQL-create-tables-in-python/](https://www.geeksforgeeks.org/postgresql-create-tables-in-python/)

本文将探索使用 Python 在 PostgreSQL 数据库中创建新表的过程。

### 用 Python 创建 PostgreSQL 表的步骤

要在 PostgreSQL 数据库中创建新表，可以使用以下步骤:

1.  First, construct the CREATE TABLE statement.
2.  Next, connect to PostgreSQL database by calling the connect () function. The function returns a connection object.
3.  Then, create a cursor object by calling the cursor () method of the connection object.
4.  Then, CREATE TABLE is executed by calling the execute () method of the cursor object.
5.  Finally, the communication with PostgreSQL database server is closed by calling the close () method of cursor and connection object.

## 创建 Python 程序–

首先，创建一个名为 create_table.py 的新文件。

其次，在 create_table.py 文件中，定义一个名为 create_tables()的新函数。

create_tables()函数在供应商数据库中创建四个表:供应商、零件、供应商零件和零件绘图。

## 蟒 3

```py
#!/usr / bin / python

import psycopg2
from config import config

def create_tables():
    """ create tables in the PostgreSQL database"""
    commands = (
        """
        CREATE TABLE vendors (
            vendor_id SERIAL PRIMARY KEY,
            vendor_name VARCHAR(255) NOT NULL
        )
        """,
        """ CREATE TABLE parts (
                part_id SERIAL PRIMARY KEY,
                part_name VARCHAR(255) NOT NULL
                )
        """,
        """
        CREATE TABLE part_drawings (
                part_id INTEGER PRIMARY KEY,
                file_extension VARCHAR(5) NOT NULL,
                drawing_data BYTEA NOT NULL,
                FOREIGN KEY (part_id)
                REFERENCES parts (part_id)
                ON UPDATE CASCADE ON DELETE CASCADE
        )
        """,
        """
        CREATE TABLE vendor_parts (
                vendor_id INTEGER NOT NULL,
                part_id INTEGER NOT NULL,
                PRIMARY KEY (vendor_id, part_id),
                FOREIGN KEY (vendor_id)
                    REFERENCES vendors (vendor_id)
                    ON UPDATE CASCADE ON DELETE CASCADE,
                FOREIGN KEY (part_id)
                    REFERENCES parts (part_id)
                    ON UPDATE CASCADE ON DELETE CASCADE
        )
        """)
    conn = None
    try:
        # read the connection parameters
        params = config()
        # connect to the PostgreSQL server
        conn = psycopg2.connect(**params)
        cur = conn.cursor()
        # create table one by one
        for command in commands:
            cur.execute(command)
        # close communication with the PostgreSQL database server
        cur.close()
        # commit the changes
        conn.commit()
    except (Exception, psycopg2.DatabaseError) as error:
        print(error)
    finally:
        if conn is not None:
            conn.close()

if __name__ == '__main__':
    create_tables()
```

## 执行 Python 程序–

要执行 Python 程序，可以使用以下命令:

```py
python create_table.py
```

## 验证表的创建–

首先，使用 psql 程序登录 PostgreSQL 数据库服务器。

其次，使用\dt 命令显示供应商数据库中的表列表。

```py
suppliers=# \dt

             List of relations
 Schema |     Name      | Type  |  Owner
--------+---------------+-------+----------
 public | part_drawings | table | postgres
 public | parts         | table | postgres
 public | vendor_parts  | table | postgres
 public | vendors       | table | postgres
(4 rows)
```

从输出中可以清楚地看到，我们在供应商数据库中成功创建了四个表。

如果您使用其他客户端工具，如 pgAdmin，您可以通过公共模式下的表列表查看这些表。