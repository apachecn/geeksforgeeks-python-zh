# Python 中的 Oracle 数据库连接

> 原文:[https://www . geesforgeks . org/Oracle-database-connection-in-python/](https://www.geeksforgeeks.org/oracle-database-connection-in-python/)

有时作为编程的一部分，我们需要使用数据库，因为我们想存储大量的信息，所以我们使用数据库，如 Oracle、MySQL 等。因此，在本文中，我们将讨论使用 Python 的 Oracle 数据库的连接性。这可以通过模块名 **cx_Oracle** 完成。

**Oracle 数据库**
为了通过我们的 Python 程序与任何数据库进行通信，我们需要一些连接器，这些连接器只不过是 *cx_Oracle* 模块。

**用于安装 CX-甲骨文:**

如果您使用 Python >= 3.6，请在 Linux 中使用以下命令:–

```
pip install cx-Oracle
```

如果您使用 Python >= 3.6，请在窗口中使用以下命令:–

```
py -m pip install cx-Oracle
```

通过此命令，您可以安装 cx-Oracle 软件包，但需要先在您的电脑上安装 Oracle 数据库。

*   **导入数据库特定模块**
    Ex。导入 cx_Oracle
*   **connect():** 现在使用 connect()函数在 Python 程序和 Oracle 数据库之间建立连接。

```
con = cx_Oracle.connect('username/password@localhost')
```

*   **cursor():** 要执行一个 SQL 查询并提供结果，需要一些特殊的对象，它只不过是 cursor()对象。

```
cursor = cx_Oracle.cursor()
```

*   **执行/executemany 方法:**

> cursor . execute(sqlquery)–––->执行单个查询。
> cursor . execute many(SQL query)–––->使用多个绑定变量/占位符执行单个查询。

*   **commit():** 用于包含更新、插入、删除等操作的 DML(数据操作语言)查询。我们需要提交()，然后只有结果反映在数据库中。
*   **胎儿、(fetchny(int)，胎儿 chall():**
    1.  fetchone():此方法用于从结果集的顶部提取一行。
    2.  fetchmany(int):该方法用于根据传入的参数获取有限数量的行。
    3.  fetchall():此方法用于从结果集中提取所有行。
*   **close():** 全部完成后，强制关闭所有操作。

```
cursor.close()
con.close()
```

## **执行 SQL 语句:**

### **1。创建表格**

## 蟒蛇 3

```
# importing module
import cx_Oracle

# Create a table in Oracle database
try:

    con = cx_Oracle.connect('tiger/scott@localhost:1521/xe')
    print(con.version)

    # Now execute the sqlquery
    cursor = con.cursor()

    # Creating a table employee
    cursor.execute("create table employee(empid integer primary key, name varchar2(30), salary number(10, 2))")

    print("Table Created successfully")

except cx_Oracle.DatabaseError as e:
    print("There is a problem with Oracle", e)

# by writing finally if any error occurs
# then also we can close the all database operation
finally:
    if cursor:
        cursor.close()
    if con:
        con.close()
```

**输出:**

```
Table Created successfully
```

DDL 语句不需要提交。它们是自动提交的。在上面的程序中，我使用了 execute()方法来执行一条 SQL 语句。

### **2。使用 execute()方法将记录插入表中**

## 蟒蛇 3

```
# importing module
import cx_Oracle

# Inserting a record into a table in Oracle database
try:
    con = cx_Oracle.connect('tiger/scott@localhost:1521/xe')
    cursor = con.cursor()

    #con.autocommit = True
    # Inserting a record into table employee
    cursor.execute('insert into employee values(10001,\'Rahul\',50000.50)')

    # commit() to make changes reflect in the database
    con.commit()
    print('Record inserted successfully')

except cx_Oracle.DatabaseError as e:
    print("There is a problem with Oracle", e)

# by writing finally if any error occurs
# then also we can close the all database operation
finally:
    if cursor:
        cursor.close()
    if con:
        con.close()
```

**输出:**

```
Record inserted successfully
```

一旦我们执行了任何 DML 语句，就需要提交事务。您可以通过两种方式提交事务:-

1.  con.commit()。这用于手动提交事务。
2.  自动提交=真。这用于自动提交事务。

### **3。使用 executemany()方法**将多个记录插入到一个**表中**

## 蟒蛇 3

```
import cx_Oracle

# Load data from a csv file into Oracle table using executemany
try:
    con = cx_Oracle.connect('tiger/scott@localhost:1521/xe')

except cx_Oracle.DatabaseError as er:
    print('There is an error in Oracle database:', er)

else:
    try:
        cur = con.cursor()
        data = [[10007, 'Vikram', 48000.0], [10008, 'Sunil', 65000.1], [10009, 'Sameer', 75000.0]]

        cur = con.cursor()
        # Inserting multiple records into employee table
        # (:1,:2,:3) are place holders. They pick data from a list supplied as argument
        cur.executemany('insert into employee values(:1,:2,:3)', data)

    except cx_Oracle.DatabaseError as er:
        print('There is an error in Oracle database:', er)

    except Exception as er:
        print(er)

    else:
        # To commit the transaction manually
        con.commit()
        print('Multiple records are inserted successfully')

finally:
    if cur:
        cur.close()
    if con:
        con.close()
```

**输出:**

```
Multiple records are inserted successfully
```

有时可能需要根据每次提供给它的不同值多次执行一条 SQL 语句。这可以使用 executemany()方法来实现。我们提供了一个包含值列表的列表，这些值将替换要执行的 SQL 查询中的占位符。

从上述情况来看

*   :1 被值 10007 替代
*   :2 被值“Vikram”替代
*   :3 被值 48000.0 替代

以此类推(给定列表中的下一个值列表)

同样，您可以提供字典列表。但是我们将使用 bind 变量(稍后讨论)来代替占位符。

### **4。使用 fetchall()、fetchmany(int)、fetchone()** 查看选择查询的结果集

## 蟒蛇 3

```
import cx_Oracle

try:
    con = cx_Oracle.connect('tiger/scott@localhost:1521/xe')

except cx_Oracle.DatabaseError as er:
    print('There is an error in the Oracle database:', er)

else:
    try:
        cur = con.cursor()

        # fetchall() is used to fetch all records from result set
        cur.execute('select * from employee')
        rows = cur.fetchall()
        print(rows)

        # fetchmany(int) is used to fetch limited number of records from result set based on integer argument passed in it
        cur.execute('select * from employee')
        rows = cur.fetchmany(3)
        print(rows)

        # fetchone() is used fetch one record from top of the result set
        cur.execute('select * from employee')
        rows = cur.fetchone()
        print(rows)

    except cx_Oracle.DatabaseError as er:
        print('There is an error in the Oracle database:', er)

    except Exception as er:
        print('Error:'+str(er))

    finally:
        if cur:
            cur.close()

finally:
    if con:
        con.close()
```

**输出:**

```
[(10001, 'Rahul', 50000.5), (10002, 'Sanoj', 40000.75), (10003, 'Soumik', 30000.25), (10004, 'Sayan', 45000.0), (10005, 'Sobhan', 60000.1), (10006, 'Gururaj', 70000.0), (10007, 'Vikram', 48000.0), (10008, 'Sunil', 65000.1), (10009, 'Sameer', 75000.0)]
[(10001, 'Rahul', 50000.5), (10002, 'Sanoj', 40000.75), (10003, 'Soumik', 30000.25)]
(10001, 'Rahul', 50000.5)
```

在上面的程序中，我们使用了 3 种方法

1.  **fetch all():***fetch all()*用于从结果集中获取所有记录。
2.  **fetch many(int):***fetch many(int)*用于根据传递给它的整数参数从结果集中获取有限数量的记录。
3.  **fetch one():***fetch one()*用于从结果集顶部获取一条记录。

### **5。使用绑定变量**查看选择查询的结果集

## 蟒蛇 3

```
import cx_Oracle

try:
    con = cx_Oracle.connect('tiger/scott@localhost:1521/xe')

except cx_Oracle.DatabaseError as er:
    print('There is error in the Oracle database:', er)

else:
    try:
        cur = con.cursor()

        cur.execute('select * from employee where salary > :sal', {'sal': 50000})
        rows = cur.fetchall()
        print(rows)

    except cx_Oracle.DatabaseError as er:
        print('There is error in the Oracle database:', er)

    except Exception as er:
        print('Error:', er)

    finally:
        if cur:
            cur.close()

finally:
    if con:
        con.close()
```

**输出:**

```
[(10001, 'Rahul', 50000.5), (10005, 'Sobhan', 60000.1), (10006, 'Gururaj', 70000.0),
 (10008, 'Sunil', 65000.1), (10009, 'Sameer', 75000.0)]
```

在这种情况下，我在 execute()方法中传递了一个字典。这个字典包含绑定变量的名称作为关键字，以及它对应的值。当执行 SQL 查询时，键中的值代替了绑定变量。