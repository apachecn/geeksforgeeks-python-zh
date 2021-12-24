# 用 Python 从 CSV 创建 sqlite 数据库

> 原文:[https://www . geeksforgeeks . org/creating-a-SQLite-database-from-CSV-with-python/](https://www.geeksforgeeks.org/creating-a-sqlite-database-from-csv-with-python/)

**先决条件:**

*   [熊猫](https://www.geeksforgeeks.org/pandas-tutorial/)
*   [SQLite](https://www.geeksforgeeks.org/introduction-to-sqlite/)

SQLite 是一个实现轻量级关系数据库管理系统的软件库。与 PostgreSQL、MySQL、Oracle 等其他关系数据库管理系统不同，它不需要服务器来运行。和应用程序直接与 SQLite 数据库交互。SQLite 通常用于小型应用程序，尤其是嵌入式系统和移动应用程序。要与 Python 中的 SQLite 数据库交互，需要 sqlite3 模块。

### 方法

*   导入模块
*   创建数据库并建立连接-

为了建立连接，我们使用 *sqlite3.connect()* 函数，该函数返回一个连接对象。传递要在此函数中创建的数据库的名称。SQLite 数据库的完整状态存储在一个带有。数据库扩展。如果未指定路径，则在当前工作目录中创建新数据库。

**语法:**

> SQLite 3 . connect(' database _ name . db ')

*   使用 read_csv()导入 csv

**语法:**

> pandas.read_csv('file_name.csv ')

*   把内容写到新的表格里-

函数*到 _sql()* 根据数据帧的记录创建一个新表。在这个函数中传递表名和连接对象。表格的列名与 CSV 文件的标题相同。默认情况下，dataframe 索引作为列写入。只需将*索引*参数切换为假，即可删除该列。此外， *if_exists* 参数指定了在表名已经被使用的情况下的行为。它可以引发错误(失败)、追加新值或替换现有表。

> 熊猫。DataFrame.to_sql(table_name，connection_object， *if_exists，index* )

*   检查表格内容-

创建一个游标对象，并执行标准的 SELECT 语句来获取新创建的表的内容。

*   紧密联系

**正在使用的 Csv 文件:**T2【stud _ data . Csv】T3

![](img/81ba58ef2bea4d91be1724cd73f4840a.png)

**程序:**

## 蟒蛇 3

```
# Import required libraries
import sqlite3
import pandas as pd

# Connect to SQLite database
conn = sqlite3.connect(r'C:\User\SQLite\University.db')

# Load CSV data into Pandas DataFrame
stud_data = pd.read_csv('stud_data.csv')
# Write the data to a sqlite table
stud_data.to_sql('student', conn, if_exists='replace', index=False)

# Create a cursor object
cur = conn.cursor()
# Fetch and display result
for row in cur.execute('SELECT * FROM student'):
    print(row)
# Close connection to SQLite database
conn.close()
```

**输出:**

![](img/5112b5eeb8c4c54b0c25445adb83c950.png)