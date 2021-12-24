# 使用 MySQL-Connector Python 连接 MySQL 数据库

> 原文:[https://www . geesforgeks . org/connect-MySQL-database-using-MySQL-connector-python/](https://www.geeksforgeeks.org/connect-mysql-database-using-mysql-connector-python/)

在使用 Python 时，我们需要使用数据库，它们可能是不同的类型，如 MySQL、SQLite、NoSQL 等。在本文中，我们将期待如何使用 MySQL 连接器/Python 连接 MySQL 数据库。
Python 的 MySQL 连接器模块用于连接 MySQL 数据库和 Python 程序，它使用 Python 数据库应用编程接口规范 v2.0 (PEP 249)来实现。它使用 Python 标准库，没有依赖关系。

## 连接到数据库

在以下示例中，我们将使用 connect()
**连接到 MySQL 数据库。示例:**

## 蟒蛇 3

```py
# Python program to connect
# to mysql database

import mysql.connector

# Connecting from the server
conn = mysql.connector.connect(user = 'username',
                               host = 'localhost',
                              database = 'database_name')

print(conn)

# Disconnecting from the server
conn.close()
```