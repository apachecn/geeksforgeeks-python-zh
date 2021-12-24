# PostgreSQL–使用 Python 将数据插入表中

> 原文:[https://www . geesforgeks . org/PostgreSQL-insert-data-in-a-table-using-python/](https://www.geeksforgeeks.org/postgresql-insert-data-into-a-table-using-python/)

在本文中，我们将研究使用 Python 向 PostgreSQL 表中插入数据的过程。为此，请遵循以下步骤:

*   **步骤 1** :使用 psycopg2 模块的 ***connect()方法连接到 PostgreSQL 数据库。***

```py
conn = psycopg2.connect(dsn)

```

*   **步骤 2:** 通过调用 ***光标()方法*** 创建一个新的光标对象

```py
cur = conn.cursor()

```

*   **步骤 3:** 现在通过运行 ***execute()方法*** 来执行 INSERT 语句

```py
cur.execute(sql, (value1,value2))

```

*   **第 4 步:**插入数据后调用 ***commit()方法*** 使更改永久化。

```py
conn.commit()

```

*   **步骤 5:** 现在终止光标和与数据库的连接。

```py
cur.close()
conn.close()

```

**示例:**

例如，我们将使用我们在文章系列的前几节中创建的*学校数据库*的*学生表*。

这里我们将创建一个 *insert_student()函数*将 student_name 行插入到学生表中:

## 蟒蛇 3

```py
#!/usr/bin/python

import psycopg2
from config import config

def insert_student(student_name):
    """ insert a new vendor into the vendors table """
    sql = """INSERT INTO students(student_name)
             VALUES(%s) RETURNING student_id;"""
    conn = None
    student_id = None
    try:
        # read database configuration
        params = config()
        # connect to the PostgreSQL database
        conn = psycopg2.connect(**params)
        # create a new cursor
        cur = conn.cursor()
        # execute the INSERT statement
        cur.execute(sql, (student_name,))
        # get the generated id back
        student_id = cur.fetchone()[0]
        # commit the changes to the database
        conn.commit()
        # close communication with the database
        cur.close()
    except (Exception, psycopg2.DatabaseError) as error:
        print(error)
    finally:
        if conn is not None:
            conn.close()

    return student_id
```

现在在 *psql* 外壳中使用以下命令来验证插入:

```py
SELECT * FROM student;

```

**输出:**

![](img/548b18607ed03e7ff827c06642ecc270.png)