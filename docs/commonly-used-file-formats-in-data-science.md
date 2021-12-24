# 数据科学中常用的文件格式

> 原文:[https://www . geesforgeks . org/常用文件格式数据科学/](https://www.geeksforgeeks.org/commonly-used-file-formats-in-data-science/)

**什么是文件格式**
文件格式是为了存储特定类型的信息而设计的，如 **CSV、XLSX** 等。文件格式还告诉计算机如何显示或处理其内容。常见的文件格式，如 **CSV、XLSX、ZIP、TXT** 等。

如果你想成为一名数据科学家，那么你必须了解不同类型的文件格式。因为数据科学是关于数据及其处理的，如果你不理解文件格式，对你来说可能会很复杂。因此，您必须了解不同的文件格式。

**不同类型的文件格式:**

**CSV:**CSV 代表逗号分隔值。此名称 CSV 文件使用逗号分隔值。在 CSV 文件中，每行都是一条数据记录，每条记录由一个或多个数据字段组成，字段之间用逗号分隔。

**代码:Python 代码读取熊猫中的 csv 文件**

```py
import pandas as pd
df = pd.read_csv("file_path / file_name.csv")
print(df)
```

**XLSX:**XLSX 文件是微软 Excel Open XML 格式的电子表格文件。它用于存储任何类型的数据，但主要用于存储财务数据和创建数学模型等。

**代码:Python 代码读取熊猫中的 xlsx 文件**

```py
import pandas as pd
df = pd.read_excel (r'file_path\\name.xlsx')
print (df)
```

**注:**

> 在 python 中读取 excel 文件之前安装 xlrd，以避免错误。您可以使用以下命令安装 xlrd。
> 
> `pip install xlrd`

**ZIP:** ZIP 文件用于数据容器，它们以压缩形式存储一个或多个文件。它广泛应用于互联网在你下载了 ZIP 文件后，你需要打开它的内容才能使用它。

**代码:Python 代码读取熊猫中的 zip 文件**

```py
import pandas as pd
df = pd.read_csv(' File_Path \\ File_Name .zip')
print(df)
```

**TXT:** TXT 文件对于以纯文本存储信息非常有用，除了基本字体和字体样式之外，没有特殊格式。它可以被任何文本编辑和其他软件程序识别。

**代码:Python 代码读取熊猫中的 txt 文件**

```py
import pandas as pd
df = pd.read_csv('File_Path \\ File_Name .txt')
print(df)
```

**JSON:** JSON 是 JavaScript 对象符号的代表。JSON 是一种标准的基于文本的格式，用于表示基于 JavaScript 对象语法的结构化数据

**代码:Python 代码读取熊猫中的 json 文件**

```py
import pandas as pd
df = pd.read_json('File_path \\ File_Name .json')
print(df)
```

**超文本标记语言:**超文本标记语言是超文本标记语言的代表，用于创建网页。我们可以使用 read_html()函数读取 python 熊猫中的 html 表。

**代码:Python 代码读取熊猫中的 html 文件**

```py
import pandas as pd
df = pd.read_html('File_Path \\File_Name.html')
print(df)
```

**注:**

> 您需要安装一个名为“lxml & html5lib”的包，该包可以用“”处理文件。' html '扩展名。
> 
> `pip install html5lib
> pip install lxml`

**PDF:** pdf 代表可移植文档格式(PDF)当我们需要保存无法修改但仍需要轻松获得的文件时，会使用这种文件格式。

**代码:Python 代码读取熊猫中的 pdf**

```py
pip install tabula-py
pip install pandas
df = tabula.read_pdf(file_path \\ file_name .pdf)
print(df)
```

**注:**

> 您需要安装一个名为“boal-py”的包，该包可以用“”处理文件。' pdf '扩展名。
> `pip install tabula-py`