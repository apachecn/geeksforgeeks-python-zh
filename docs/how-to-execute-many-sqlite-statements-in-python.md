# 如何在 Python 中执行多条 SQLite 语句？

> 原文:[https://www . geeksforgeeks . org/如何在 python 中执行多条 sqlite 语句/](https://www.geeksforgeeks.org/how-to-execute-many-sqlite-statements-in-python/)

在使用 executescript()方法的 SQLite 中，我们可以同时执行多个 SQL 语句/查询。基本的 execute()方法允许我们一次只接受一个查询，因此当您需要执行几个查询时，我们需要像脚本一样排列它们，并将该脚本传递给 executescript()方法。

executescript()可以连续执行一系列几个 SQL/SQLite 查询。executescript()操作运行时，其他线程/操作在 executescript()完成所有查询之前无法访问数据库。如果我们需要为 executescript()中的每个查询提供一些运行时参数，我们不能在运行时添加外部参数，因为 executescript()方法在运行时不接受查询的任何参数，因此您需要将一组静态查询作为脚本给出。在 executescript()方法的执行过程中，首先发出一条 COMMIT 语句，然后执行 SQL/SQLite 脚本。

**语法:**

```
cursor_obj.executescript(""" 
    SQLite Statement/Query . . . 1
    SQLite Statement/Query . . . 2
    SQLite Statement/Query . . . 3
    .
    .
    .
    SQLite Statement/Query . . . n 
""")
```

**下面的代码展示了如何用 python 执行多个 SQLite 语句/查询:**

## python 3

```
import sqlite3 

# make the database connection and cursor object
connection = sqlite3.connect("CollegeData.db")
cursor = connection.cursor()

# create a set of queries in executescript()
# below set of queries will create and insert
# data into table
cursor.executescript(""" 
    CREATE TABLE department( deptId INTEGER,
    deptName VARCHAR(20), deptScore INTEGER); 

    INSERT INTO department VALUES ( 01,'IT', 850 );
    INSERT INTO department VALUES ( 02,'COMP', 840 );
    INSERT INTO department VALUES ( 03,'CIVIL', 500 );
    INSERT INTO department VALUES ( 04,'E&TC', 650 );
""")

# fetch the table data
print("Table data :")
cursor.execute("SELECT * FROM department") 
print(cursor.fetchall())

# below set of queries will update the data
# of in the table
cursor.executescript("""
    UPDATE department set deptScore = 900 where deptId = 01;
    UPDATE department set deptScore = 890 where deptId = 02;
    UPDATE department set deptScore = 660 where deptId = 03;
    UPDATE department set deptScore = 790 where deptId = 04;
""")

# fetch the table data after updation
print("Table data after updation :")
cursor.execute("SELECT * FROM department") 
print(cursor.fetchall())

# commit the changes and close the database
# connection 
connection.commit() 
connection.close()
```

**输出**

> 表数据:
> 
> [(1，‘IT’，850)，(2，‘COMP’，840)，(3，‘CIVIL’，500)，(4，‘E&TC’，650)]
> 
> 表数据更新后:
> 
> [(1，‘IT’，900)，(2，‘COMP’，890)，(3，‘CIVIL’，660)，(4，‘E&TC’，790)]

上面的代码一次执行多个 SQLite 语句。代码中的第一个 executescript()方法在一个实例中创建和插入数据到表中。然后 second executescript()方法更新一个实例中的所有记录。这样，可以使用 executescript()在 SQLite 中执行一组许多查询。