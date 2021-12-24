# 如何使用 Python 创建 SQLite 数据库的备份？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 创建 sqlite 数据库备份/](https://www.geeksforgeeks.org/how-to-create-a-backup-of-a-sqlite-database-using-python/)

在本文中，我们将学习如何使用 Python 创建 SQLite 数据库的备份。要使用 Python 创建 SQLite 数据库的备份，需要的模块是 **SQLite3** 和 **IO** 。

首先，让我们按照下面的程序创建原始数据库:

## python 3

```
import sqlite3
import io
from sqlite3 import Error

def SQLite_connection():

    try:    
        conn = sqlite3.connect('Originaldatabase.db')
        print("Connection is established successfully!")
        print("'originaldatabase.db' is created ")
        return conn

    except Error:
        print(Error)

    finally:
        conn.close()

SQLite_connection()
```