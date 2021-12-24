# 如何在 Python 中将 Excel 转换成 XML 格式？

> 原文:[https://www . geesforgeks . org/如何将 excel 转换为 python 中的 xml 格式/](https://www.geeksforgeeks.org/how-to-convert-excel-to-xml-format-in-python/)

当需要将文件从一种格式转换为另一种格式时，Python 被证明是一种强大的语言。它支持可以用来轻松实现功能的工具。在本文中，我们将了解如何使用 Python 将 Excel 文件转换为可扩展术语(XML)文件。

### 需要的模块

*   **OpenPyXL** 有助于与 Excel 文件交互。它可以读写。xlsx 和。xlsm 文件，可以安装为:

> pip 安装 openpyxl

*   **Yattag** 是一个 Python 库，用于用 Python 以非常易读的方式生成 HTML 或 XML 文档。这个 Yattag 库非常简单，易于使用。如果您正在搜索任何库，以便更容易地生成 HTML 或 XML 文档。

> pip 安装 yattag

### 所需功能

*   要加载 Excel 文件的内容**使用 OpenPyXl 的 load_workbook()** 方法。
*   使用具有适当属性的 Iter_rows() 来迭代加载的文件并读取数据

> **语法:**Iter _ row(min _ col，min_row，max_col，max_row，values_only)
> 
> **参数:**
> 
> *   **min _ col(int)**–最小列值(基于 1 的索引)
> *   **min _ row(int)**–最小行值(基于 1 的索引)
> *   **max _ col(int)**–最大列值(基于 1 的索引)
> *   **Max _ row(int)**–最大行值(基于 1 的索引)
> *   **values _ only(bool)**–是否只返回单元格值

*   **tagtext()** 方法是一个辅助方法，**返回一个** **三元组**，由以下内容组成:
    *   **文档**实例本身
    *   单据实例的**标记**方法
    *   单据实例的**文本**方法
*   **asis** 方法将字符串附加到文档中，没有任何形式的转义。
*   **标记**方法将接受任何字符串作为标记名。
*   函数的作用是:获取一个表示 XML 或 HTML 文档的字符串，并返回该文档的缩进版本。

**正在使用的数据库:** [点击此处](https://drive.google.com/file/d/1FCjd5FtxxRRGG0CtYTzZ9FmNw_0f_zU1/view?usp=sharing)

要先将 Excel 数据转换成 XML，需要先读取，给定的程序解释了读取数据的机制。

**接近**

*   导入模块
*   加载 Excel 文件
*   创建工作表对象
*   遍历行

**例**

## 蟒蛇 3

```py
# Install the openpyxl library
from openpyxl import load_workbook

# Loading our Excel file
wb = load_workbook("demo_database.xlsx")

# creating the sheet 1 object
ws = wb.worksheets[0]

# Iterating rows for getting the values of each row
for row in ws.iter_rows(min_row=1, max_row=2, min_col=1, max_col=6):
    print([cell.value for cell in row])
```

现在，一旦我们读完数据。让我们编写如何将 Excel 转换为 XML 格式的代码，

**进场:**

*   导入模块
*   读出数据
*   创建 XML 格式页面
*   追加到文件
*   保存文件

**示例:**

## 蟒蛇 3

```py
from openpyxl import load_workbook
from yattag import Doc, indent

# Load our Excel File
wb = load_workbook("demo_database.xlsx")
# Getting an object of active sheet 1
ws = wb.worksheets[0]

# Returning returns a triplet
doc, tag, text = Doc().tagtext()

xml_header = '<?xml version="1.0" encoding="UTF-8"?>'
xml_schema = '<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"></xs:schema>'

# Appends the String to document
doc.asis(xml_header)
doc.asis(xml_schema)

with tag('People'):
    for row in ws.iter_rows(min_row=2, max_row=10, min_col=1, max_col=6):
        row = [cell.value for cell in row]
        with tag("Person"):
            with tag("First_Name"):
                text(row[0])
            with tag("Last_Name"):
                text(row[1])
            with tag("Gender"):
                text(row[2])
            with tag("Country"):
                text(row[3])
            with tag("Age"):
                text(row[4])
            with tag("Date"):
                text(row[5])

result = indent(
    doc.getvalue(),
    indentation='   ',
    indent_text=True
)

with open("output.xml", "w") as f:
    f.write(result)
```

**输出:** [输出](https://drive.google.com/file/d/1Uq6WeEqj_uu0NJvuMZqMeoYlLE0xTnZ4/view?usp=sharing)