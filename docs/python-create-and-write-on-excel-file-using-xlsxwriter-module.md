# Python |使用 xlsxwriter 模块

在 excel 文件上创建和写入

> 原文:[https://www . geesforgeks . org/python-在 excel 上创建并写入文件-使用-xlsxwriter-module/](https://www.geeksforgeeks.org/python-create-and-write-on-excel-file-using-xlsxwriter-module/)

**XlsxWriter** 是一个 Python 模块，用于以 XLSX 文件格式编写文件。它可用于将文本、数字和公式写入多个工作表。此外，它还支持格式、图像、图表、页面设置、自动过滤器、条件格式等功能。
使用此命令安装 xlsxwriter 模块:

```
 pip install xlsxwriter 
```

**注意:**在整个 XlsxWriter 中，行和列是零索引的。工作表中的第一个单元格，A1 是(0，0)，B1 是(0，1)，A2 是(1，0)，B2 是(1，1)..所有人都一样。
让我们看看如何使用 Python 创建和写入 excel 工作表。
**代码#1 :** 使用 A1 符号(单元格名称)在特定单元格中写入数据。

## 蟒蛇 3

```
# import xlsxwriter module
import xlsxwriter

# Workbook() takes one, non-optional, argument
# which is the filename that we want to create.
workbook = xlsxwriter.Workbook('hello.xlsx')

# The workbook object is then used to add new
# worksheet via the add_worksheet() method.
worksheet = workbook.add_worksheet()

# Use the worksheet object to write
# data via the write() method.
worksheet.write('A1', 'Hello..')
worksheet.write('B1', 'Geeks')
worksheet.write('C1', 'For')
worksheet.write('D1', 'Geeks')

# Finally, close the Excel file
# via the close() method.
workbook.close()
```