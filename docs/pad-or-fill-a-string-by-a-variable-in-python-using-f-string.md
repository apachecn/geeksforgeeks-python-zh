# 使用 f-string 在 Python 中用变量填充或填充字符串

> 原文:[https://www . geesforgeks . org/pad-or-fill-a-string-by-a-variable-in-python-using-f-string/](https://www.geeksforgeeks.org/pad-or-fill-a-string-by-a-variable-in-python-using-f-string/)

**f-string** 代表格式化字符串。它是在 Python 版本中出现的，并很快被用来对字符串进行简单的格式化。F-string 是一个字符串，其语法以 f 开头，后跟{}。用于保存变量的占位符，将根据变量名及其值分别进行更改。

已经有字符串格式可用，如**%-格式化**、 **`str.format()`** 或`**string.Template**()`。使用这些存在的主要缺点是它不太容易执行，所以 Python 添加了 f-string，因为它很容易用最少的语法实现。

例如，考虑所有 3 个变量:
**1。使用%-格式化**

```
name = 'nightfury1'
print('%s is GeeksforGeeks a contributor' % (name))
```

**输出:**

```
nightfury1 is GeeksforGeeks a contributor.
```

**2。使用 str.format()**

```
name = 'nightfury1'
print('{} is GeeksforGeeks a contributor.'.format(name))
```

**输出:**

```
nightfury1 is GeeksforGeeks a contributor.
```

**3。使用 f 弦**

```
name = 'nightfury1'
print(f'{name} is GeeksforGeeks a contributor.')
```

**输出:**

```
nightfury1 is GeeksforGeeks a contributor.
```

### 使用 f-string 的方法:

**1。f-string 表达式:**它计算{}内部的字符串并返回值。

```
name = 'nightfury1'
post = 'Technical Content Writer Intern.'
print(f'{name} is GeeksforGeeks {post}')
```

**输出:**

```
nightfury1 is Geeksforgeeks Technical Content Writer Intern
```

**2。f-string 字典:**因为字典包含键值属性。因此，f-string 使用字典的属性进行字符串格式化。

```
GfG = {'name' : 'nightfury1',
       'post' : 'Technical Content Writer Intern'}
print(f'{GfG["name"]} is GeeksforGeeks {GfG["post"]}.')
```

**输出:**

```
nightfury1 is Geeksforgeeks Technical Content Writer Intern.
```

**3。f-string debug :** 调试给定表达式内部的值计算输出。

```
import math
x = 0.5

print(f'math.cos({x}) = {math.cos(x)}')
print(f'math.sin({x}) = {math.sin(x)}')
```

**输出:**

```
math.cos(0.5) = 0.8775825618903728
math.sin(0.5) = 0.479425538604203

```

**4。f-string multiline:**f-string 被放在圆括号中，因此它对它们求值，每个字符串前面都有 f 字符，并以多行形式返回结果。

```
name = 'nightfury1'
org = 'GeeksforGeeks'
post = 'Technical Content Writer Intern'

gfg = (f'Name : {name}\n'
       f'Organization : {org}\n'
       f'Post : {post}.')

print(gfg)
```

**输出:**

```
Name : nightfury1
Organization : GeeksforGeeks
Post : Technical Content Writer Intern.

```

### 使用 f 字符串填充和填充:

我们可以在十进制或给定的数字或日期时间之后输入并指定数字格式，这称为 f-string 填充。

**1。0-填充:**这里，我们通过在 f-string {}语法中添加`{variable : 0N}`来应用 0-填充，其中 N 是指数字的总数。

```
for i in range(1, 5):
    print(f'The number is {i:02}')
```

**输出:**

```
The number is 01
The number is 02
The number is 03
The number is 04

```

**2。日期填充:**在这里，我们还通过使用日期时间模块来设置日期的格式，并在{}中添加所需的格式，如`{date : directive}`。

```
import datetime
now = datetime.datetime.now()
print(f'Current Time : {now : %Y-%m-%d %H:%M}')
```

**输出:**

```
Current Time :  2020-08-02 19:34

```

**3。空格填充:**这里，我们将空格应用于像`{variable : N}`这样的字符串，其中 N 是总长度。因此，如果给定的变量是“a”，N 是 4，那么它将在给定的变量之前添加额外的空格。

```
for i in range(1, 5):
    print(f'The number is {i : 4}')
```

**输出:**

```
The number is    1
The number is    2
The number is    3
The number is    4

```

**4。**正如我们所知，默认情况下，字符串向左对齐。但是在 f-strings 的帮助下，我们可以通过使用`{variable : >N}`来证明它们是正确的，其中 N 是总长度。

```
s1 = 'Geeksforgeeks'
s2 = 'ksforgeeks'
s3 = 'forgeeks'
s4 = 'geeks'

print(f'{s1 : >13}')
print(f'{s2 : >13}')
print(f'{s3 : >13}')
print(f'{s4 : >13}')
```

**输出:**

```
Geeksforgeeks
   ksforgeeks
     forgeeks
        geeks

```

我们可以在给定字符串的前后用数字或符号输入和指定格式，这称为 f-string 填充。

**1。硬编码–填充:**这里我们在 f-string 语法中添加符号或填充符作为硬编码。

```
# left filling
print(f'{"geeks" :*>15}')

# right filling
print(f'{"geeks" :*<15}')
```

**输出:**

```
**********geeks
geeks**********

```

**2。变量–填充:**这里我们在 print()函数中使用了 f-string 填充花括号表达式。

```
width = 15
filler = '*'
for i in range(6, width):
    print(f'{"geeks" :{filler}<{i}}')
```

**输出:**

```
geeks*
geeks**
geeks***
geeks****
geeks*****
geeks******
geeks*******
geeks********
geeks*********

```

**f 弦的优势:**

1.  它是 Python 中最快的字符串格式化方法。
2.  可读性更强。
3.  本质上是简洁的。
4.  它不太容易出错，这意味着在格式化字符串时出错的机会更少。
5.  它不太冗长，即在格式中包含较少的语法。