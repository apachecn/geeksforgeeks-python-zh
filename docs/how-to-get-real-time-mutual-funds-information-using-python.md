# 如何使用 Python 获取实时的共同基金信息？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 获得实时共同基金信息/](https://www.geeksforgeeks.org/how-to-get-real-time-mutual-funds-information-using-python/)

在本文中，我们将为实时共同基金信息编写 Python 脚本。今天，共同基金是投资者中非常流行的术语，所以让我们为他们做一些帮助。多功能工具模块将有助于从共同基金协会收集实时数据。

**Mftool 功能:**

*   Use the scheme code to get the latest updated quotation from mutual funds.
*   Get all available registration schemes of AMF.
*   Get the NAV tracking record.
*   Get a list of all schemes with scheme codes.

注:本模块能够从印度共同基金协会收集数据。

**开始之前我们需要安装这个模块:**

将此模块运行到您的终端中。

```py
pip install mftool

```

**让我们一步步了解这些模块:**

**第 1 步:**导入模块并为多功能工具创建一个对象。

## 蟒 3

```py
# import module
from mftool import Mftool

obj = Mftool()
```

**第二步:**用 **get_scheme_quote()** 方法获取方案报价。

**注:**所有方案编码在此呈现:[点击](https://raw.githubusercontent.com/NayakwadiS/mftool/master/Scheme_codes.txt)

## 蟒 3

```py
# pass the scheme code into 
# methods
data = obj.get_scheme_quote('119551')
print(data)
```