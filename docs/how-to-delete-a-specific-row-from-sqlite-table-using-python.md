# 如何使用 Python 从 SQLite 表中删除特定行？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 从 sqlite 表中删除特定行/](https://www.geeksforgeeks.org/how-to-delete-a-specific-row-from-sqlite-table-using-python/)

在本文中，我们将讨论如何使用 Python 从 SQLite 表中删除特定行。

为了从 SQL 中的表中删除特定的行，我们使用 **delete 查询**，SQL 中的 DELETE 语句用于从表中删除现有的记录。根据我们在 WHERE 子句中指定的条件，我们可以删除一条记录或多条记录。

**语法:**

> 从表名中删除
> 
> WHERE 条件；

我们将创建一个表，然后在其中执行删除操作。

## 蟒 3

```py
# importing sqlite module
import sqlite3

# create connection to the database 
# my_database
connection = sqlite3.connect('my_database.db')

# create table named address of customers 
# with 4 columns id,name age and address
connection.execute('''CREATE TABLE ship (ship_id INT, ship_name \
TEXT NOT NULL, ship_destination CHAR(50) NOT NULL); ''')

print("Ship table created successfully")

# close the connection
connection.close()
```

**输出:**

```py
Ship table created successfully
```

**例 1:**

Python 程序插入数据和删除数据，其中 2 是发货 id。

## 蟒 3

```py
# import sqlite module database
import sqlite3

# create connection to the database
# my_database
connection = sqlite3.connect('my_database.db')

# insert query to insert values
connection.execute("INSERT INTO ship  VALUES (1, 'tata-hitachi','noida' )")
connection.execute("INSERT INTO ship  VALUES (2, 'tata-mumbai','mumbai' )")
connection.execute("INSERT INTO ship  VALUES (3, 'tata-express','hyderabad' )")

# query to display all data in the table
cursor = connection.execute("SELECT * from ship")
print("Actual data")

# display row by row
for row in cursor:
    print(row)

# query to delete all data where ship_id = 2
connection.execute("DELETE from ship where ship_id=2")

print("After  deleting ship id = 2 row")

# display row by row
cursor = connection.execute("SELECT * from ship")
for row in cursor:
    print(row)

# close the connection
connection.close()
```