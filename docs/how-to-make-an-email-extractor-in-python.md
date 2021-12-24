# 如何用 Python 制作邮件提取器？

> 原文:[https://www . geesforgeks . org/如何制作 python 电子邮件提取器/](https://www.geeksforgeeks.org/how-to-make-an-email-extractor-in-python/)

在本文中，我们将看到如何使用 python 和 regex 提取文本中的所有有效电子邮件。

*   正则表达式简称为 regex 或 regexp(也称为有理表达式)是一个描述搜索模式的字符链。通常，字符串查找算法使用这种样式对字符串进行“定位”或“定位并替换”操作，或者输入验证。
*   它是由理论计算机技术和自然语言理论发展而来的一种方法。
*   python 中的 re 模块完全支持 Python 中类似 Perl 的正则表达式。它提供了一组允许我们搜索匹配字符串的函数。
*   re python 模块中定义的 **re.findall()** 函数接受两个参数，并返回找到的所有匹配字符串的列表。

> **语法:** re.findall(正则表达式，字符串)
> 
> **参数:**
> 
> *   正则表达式由各种预定义的符号组成，用于搜索我们正在寻找的模式。
> *   该字符串是我们要对其执行搜索操作的原始字符串。

导入必要的模块后，我们将调用 re 模块中定义的 findall()方法来查找与作为参数传递的 regex 表达式匹配的所有字符串。

正则表达式可以分为三个部分:

**1 .** **r"[A-Za-z0-9_%+-。]+**

该表达式查找由 a-z 定义的所有大写字母、小写字母 A-Z、所有数字 0-9 和特殊字符(如 _%+-)组成的连续字符序列。。“+”用于将第二个正则表达式附加到第一个正则表达式上。

**2 .****【r】@[a-za-z0-9。[-]T3]**

该表达式寻找由 a-z 定义的所有大写字母、小写字母 A-Z、所有数字 0-9 和特殊字符(如)组成的连续字符序列。_.“+”用于将第二个正则表达式附加到第一个正则表达式上。

**3 .** **r"\。[a-za-z]{ 2.5 } "**

这个表达式寻找由 a-z 定义的所有大写字母和小写字母 A-Z 组成的连续字符序列，使得这个连续序列的大小在 2-5 之间(包括 2 和 5)。

**示例 1:从字符串中提取有效的电子邮件**

## 蟒蛇 3

```py
# Raw text
text = "Duis info@geeksforgeeks.com convallis. Parturient montes nascetur ridiculus mus \
geeksforgeeks@rocks.xyz mauris. Odio eu feugiat pre@rsos_tium.index nibh ipsum consequat love@gfg.in \
pretium aenean pharetra magna ac placerat. Vitae justo eget magna fermentum iaculis eu non."

#import regex module
import re

#finding all valid emails using regex
reg = re.findall(r"[A-Za-z0-9_%+-.]+"
                 r"@[A-Za-z0-9.-]+"
                 r"\.[A-Za-z]{2,5}",text)

#printing all the valid emails found
print(reg)
```

**输出:**

```py
['info@geeksforgeeks.com', 'geeksforgeeks@rocks.xyz', 'love@gfg.in']
```

**示例 2:从** [**文本文件**](https://drive.google.com/file/d/1dWjmxoG4uxtHgUvIZ6mQ6sN9ECiM6Xlq/view?usp=sharing) 中提取有效电子邮件

使用 open()函数，我们以“r”模式打开所需文件，只读模式。对于每一行，我们剥离该行，以便删除空白，并与第一个示例类似地处理它们。

## 蟒蛇 3

```py
#importing module
import re

with open('sample.txt','r') as file:
  for line in file:
    line = line.strip()

    # finding all valid emails
    reg = re.findall(r"[A-Za-z0-9_%+-.]+"
                      r"@[A-Za-z0-9.-]+ "
                      r"\.[A-Za-z]{2,5}",line)

#printing all the valid emails found
print(reg)
```

**输出:**

```py
['info@geeksforgeeks.com', 'geeksforgeeks@rocks.xyz', 'love@gfg.in']
```