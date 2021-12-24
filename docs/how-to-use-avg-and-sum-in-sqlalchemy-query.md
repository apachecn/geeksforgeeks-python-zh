# 如何在 SQLAlchemy 查询中使用平均值和总和？

> 原文:[https://www . geesforgeks . org/如何使用-avg-and-sum-in-sqlalchemy-query/](https://www.geeksforgeeks.org/how-to-use-avg-and-sum-in-sqlalchemy-query/)

在本文中，我们将看到如何使用 Python 在 SQLAlchemy 查询中使用 avg 和 sum。

## 安装 SQLAlchemy

SQLAlchemy 可通过 pip 安装包获得。

```py
pip install sqlalchemy
```

但是，如果您正在使用 flask，您可以使用它自己的 SQLAlchemy 实现。它可以通过以下方式安装–

```py
pip install flask-sqlalchemy
```

### 例子

在我们继续之前，我们需要有一个数据库和一个表来使用。对于这个例子，我们使用了 MySQL 数据库，并创建了一个**学生**表。该表有 3 列和 6 条记录，如下所示。

![](img/5e2761e2bb6800a7e817e9b0994ceb57.png)

在表中，我们有一个浮动列**` percent`**，我们将使用 SQLAlchemy 对其执行平均和求和操作。

### **进场:**

1.  首先，为了简单起见，我们将 sqlalchemy 库导入为 **db** 。所有 sqlalchemy 对象、方法等都将使用 **db** 前缀导入，以提高清晰度。
2.  然后我们创建引擎，它将作为数据库的连接来执行所有的数据库操作。
3.  创建元数据对象。元数据对象“元数据”包含关于我们数据库的所有信息。
4.  使用元数据信息从数据库中获取**学生**表。
5.  我们现在可以编写一个 SQLAlchemy 查询来获取所需的记录。我们首先使用 SQLalchemy 的 **`func.avg()`** 函数提取**百分比**列的平均值。然后我们使用 **`func.sum()`** 函数来获取**百分比**列中的值的总和。请注意，在这两种情况下，我们都使用方法 **`func.round(val，2)`** 将值四舍五入到小数点后两位。
6.  打印输出。在输出中，我们可以看到**百分比**字段的总和和平均值。

### **下面是实现:**

## 计算机编程语言

```py
import sqlalchemy as db

# Define the Engine (Connection Object)
engine = db.create_engine(
    "mysql+pymysql://root:password@localhost/Geeks4Geeks")

# Create the Metadata Object
meta_data = db.MetaData(bind=engine)
db.MetaData.reflect(meta_data)

# Get the `students` table from the Metadata object
STUDENTS = meta_data.tables['students']

# SQLAlchemy Query to get AVG
query = db.select([db.func.round(db.func.avg(STUDENTS.c.percentage), 2)])

# Fetch the records
avg_result = engine.execute(query).fetchall()

# SQLAlchemy Query to get SUM
query = db.select([db.func.round(db.func.sum(STUDENTS.c.percentage), 2)])

# Fetch the records
sum_result = engine.execute(query).fetchall()

# View the records
print("\nAverage: ", avg_result[0])
print("\nSum: ", sum_result[0])
```

**输出:**

![](img/bdf12c02546fa9346db7246d59e23593.png)