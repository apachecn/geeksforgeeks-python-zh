# 使用 Python 中的名称工具模块比较和管理名称

> 原文:[https://www . geesforgeks . org/比较和管理名称-使用名称-工具-python 中的模块/](https://www.geeksforgeeks.org/comparing-and-managing-names-using-name-tools-module-in-python/)

在处理文档时，我们可能会遇到需要处理名称的问题。本文讨论的 ***名称-工具库*** 可以帮助执行此任务。它可以用来管理和比较姓名。它目前包括英语和西式名称。

### 安装:

使用以下命令安装名称工具库:

```py
pip install name_tools
```

**示例 1:使用 split()**

split()用于将姓名分为 4 个部分，即前缀(Mr、Dr 等)、名字、中间名和后缀(Jr、II 等)。

## 蟒蛇 3

```py
import name_tools

# examples to split name
name1 = name_tools.split("Mr. Sandeep Jain Sr.")
print(name1)

# examples to split name
name2 = name_tools.split("Mr. Manjeet Singh")
print(name2)

# examples to split name
name3 = name_tools.split("Dr. Robert D III")
print(name3)
```

**输出:**

```py
('Mr.', 'Sandeep', 'Jain', 'Sr.')
('Mr.', 'Manjeet', 'Singh', '')
('Dr.', 'Robert', 'D', 'III')
```

**示例 2:使用规范化()**

该函数将名称转换为标准格式:“前缀在前，后缀在后”。空格被转义，单词被大写。

## 蟒蛇 3

```py
import name_tools

print("Demonstrating Canonicalize : ")
# examples to canonicalize name
# returns String
name1 = name_tools.canonicalize("mr. sandeep jain, sr.")
print(name1)

# examples to canonicalize name
# returns String
name2 = name_tools.canonicalize("mr. manjeet Singh")
print(name2)

# examples to canonicalize name
# returns String
name3 = name_tools.canonicalize("dr.  robert d 3")
print(name3)
```

**输出:**

```py
Mr. Sandeep Jain, Sr.
Mr. Manjeet Singh
Dr. Robert D 3
```

**例 3:比较名称**

姓名比较使用 match()完成，它采用两个姓名，并与词序、首字母、敬称和头衔等因素进行比较。给每个因素一个特定的权重。

## 蟒蛇 3

```py
import name_tools

print("Demonstrating Matching names : ")

# examples to match name
# returns percentage similarity
match1 = name_tools.match("Mr Sandeep", "Sandeep")
print(match1)

match2 = name_tools.match("Mr. Sandeep Jain", "Dr. Sandeep Jain")
print(match2)

match3 = name_tools.match("Mr. Jain Sandeep", "Mr. Sandeep Jain")
print(match3)
```

**输出:**

```py
0.95
0.8999999999999999
0.0
```