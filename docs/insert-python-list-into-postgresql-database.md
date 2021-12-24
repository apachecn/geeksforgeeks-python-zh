# 将 Python 列表插入 PostgreSQL 数据库

> 原文:[https://www . geesforgeks . org/insert-python-list-into-PostgreSQL-database/](https://www.geeksforgeeks.org/insert-python-list-into-postgresql-database/)

在本文中，我们将讨论如何使用 pyscopg2 模块将 Python 列表插入 PostgreSQL 数据库。

Psycopg2 是 Python 编程语言最流行的 PostgreSQL 适配器。Psycopg2 是一个符合 DB API 2.0 的 PostgreSQL 驱动程序，目前正在积极开发中。它是为多线程应用程序设计的，并管理自己的连接池。可以使用给定的命令安装该模块:

```py
pip install psycopg2
```

要插入所有记录，将遍历列表并逐个插入值。

**语法:**

```py
list = [(),(),.....,()]
for d in list:
    cursor.execute("INSERT into *table_name*(
    column1,column2, colum3.....) VALUES (%s, %s, %s,.....)", d)
```

首先将所有需要的库导入工作空间，并建立数据库连接。将自动提交设置为 false，并创建一个光标对象。现在，创建一个要插入到表中的数据列表。遍历列表并插入值。提交并关闭连接。

**示例:**将列表值插入数据库

## 蟒蛇 3

```py
# importing psycopg2 module
import psycopg2

# establishing the connection
conn = psycopg2.connect(
    database="postgres",
    user='postgres',
    password='password',
    host='localhost',
    port='5432'
)

# creating a cursor object
cursor = conn.cursor()

# creating table
sql = '''CREATE TABLE employee(
 id  SERIAL NOT NULL,
 name varchar(20) not null,
 state varchar(20) not null
)'''

# list that contain records to be inserted into table
data = [('Babita', 'Bihar'), ('Anushka', 'Hyderabad'), 
        ('Anamika', 'Banglore'), ('Sanaya', 'Pune'),
        ('Radha', 'Chandigarh')]

# inserting record into employee table
for d in data:
    cursor.execute("INSERT into employee(name, state) VALUES (%s, %s)", d)

print("List has been inserted to employee table successfully...")

# Commit your changes in the database
conn.commit()

# Closing the connection
conn.close()
```

**输出:**

> 列表已成功插入员工表

**示例:**检查员工表中是否显示数据。

## 蟒蛇 3

```py
# importing psycopg2 module
import psycopg2

# establishing the connection
conn = psycopg2.connect(
    database="postgres",
    user='postgres',
    password='password',
    host='localhost',
    port='5432'
)

# creating cursor object
cursor = conn.cursor()

# query to sort table by name
sql2 = 'select * from employee;'
# executing query
cursor.execute(sql2)

# fetching the result
print(cursor.fetchall())

# Commit your changes in the database
conn.commit()

# Closing the connection
conn.close()
```

**输出**

> [(1，‘Babita’，‘Bihar’，(2，‘Anushka’，‘Hyderabad’，(3，‘Anamika’，‘bang ore’)，(4，‘Sanaya’，‘Pune’，(5，‘Radha’，‘Chandigarh’)]