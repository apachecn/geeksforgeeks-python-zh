# 如何在 Sqlite 表中存储 Python 函数？

> 原文:[https://www . geesforgeks . org/how-store-python-functions-in-a-SQLite-table/](https://www.geeksforgeeks.org/how-to-store-python-functions-in-a-sqlite-table/)

SQLite 是一个包含在 C 库中的关系数据库系统，其语法与 SQL 非常相似。借助 *sqlite3* 模块可以与 Python 融合。Python 标准库 *sqlite3* 是由格哈德·哈林开发的。它提供了一个符合 PEP 249 描述的数据库应用编程接口 2.0 规范的 SQL 接口。

**使用该模块并与数据库建立连接:-**

**1。**导入 *sqlite3* 模块，创建代表数据库的对象。

```
import sqlite3
conn = sqlite3.connect('function.db')

```

**2。**要执行 SQL 命令，构造一个游标对象并调用 *execute()* 方法。

```
c = conn.cursor()
c.execute('''CREATE TABLE student
             (Number REAL,stud_name TEXT)''')

```

**注意:**为了在数据库级别跟踪操作，我们需要下载 SQLite 浏览器数据库。

**在 SQLite 表中存储 Python 函数的步骤:**

*   **Step 1)** Import *sqlite3* and create the object of database **.**

## 蟒 3

```
import sqlite3
conn = sqlite3.connect('function.db')
```

这里导入了 *sqlite3* 模块，初始化了数据库 *function.db* 。如果数据库不存在，并且如果与定义的名称相同的数据库存在，此指令将创建数据库，然后它将进一步移动。

*   **Step 2)** Create a Cursor object and call its execute () method to create a table.

## 蟒 3

```
c = conn.cursor()
c.execute('''CREATE TABLE pyfuction
             (func_defination TEXT)''')
```

初始化数据库后，我们必须使用 *conn.cursor()* 创建游标对象。光标允许我们执行 SQL 命令。

*   **Step 3)** Write the function in the following syntax.

## 蟒 3

```
code = """ def gfg(): print("GeeksforGeeks") """
```