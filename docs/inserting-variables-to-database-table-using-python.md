# 使用 Python 将变量插入数据库表

> 原文:[https://www . geeksforgeeks . org/insert-variables-to-database-table-using-python/](https://www.geeksforgeeks.org/inserting-variables-to-database-table-using-python/)

在本文中，我们将看到如何使用变量插入用户数据。
在这里，我们使用 ***sqlite 模块*** 来处理数据库，但在此之前，我们需要导入该包。

```py
import sqlite3
```

要查看数据库级别的操作，只需下载 **SQLite 浏览器数据库**。
**注:**在演示中，我们使用了某些值，但您可以输入这些值来代替样本值。
**在数据库中创建和插入变量的步骤**
**代码#1:** 创建数据库

## 蟒蛇 3

```py
conn = sqlite3.connect('pythonDB.db')
c = conn.cursor()
```