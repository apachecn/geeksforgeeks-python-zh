# Python 作为关键字

> 原文:[https://www.geeksforgeeks.org/python-as-keyword/](https://www.geeksforgeeks.org/python-as-keyword/)

在本文中，我们将看到“as”关键字。关键字“as”用于在 python 中创建别名。

**带‘as’关键字的优势:**

*   当我们不能使用赋值操作符时，比如在导入模块中，这很有用。
*   它让代码更容易被人类理解。
*   关键字 as 用于与程序员选择的名称形成别名，它减少了模块名称与变量名重合的机会。

### 演示“as”关键字的工作概念:

#### **示例 1:为**模块**创建别名**

关键字“as”总是在它是别名的资源之后。“as”关键字与 import 语句配合使用，为资源分配别名:

## 蟒蛇 3

```
# Python code to demonstrait
# 'as' keyword

# Import random module with alias
import random as geek

# Function showing working of as keyword
def Geek_Func():

    # Using random module with alias
    geek_RandomNumber = geek.randint(5, 10)
    geek_RandomNumber2 = geek.randint(1, 5)

    # Printing our number
    print(geek_RandomNumber)
    print(geek_RandomNumber2)

Geek_Func()
```

**输出:**

```
9
1
```

#### **示例 2:与** a **文件**一样

关键字“as”由带有 open 语句的使用，以作为其资源的别名。在示例. txt 文件中，这里有文本“你好，极客”。

## 蟒蛇 3

```
# Python code to demonstrait
# 'as' keyword

def geek_Func():

    # With statement with geek alias
    with open('sample.txt') as geek:

        # reading text with aias
        geek_read = geek.read()

    # Printing our text
    print("Text read with alias:")
    print(geek_read)

geek_Func()
```

**输出:**

```
Text read with alias:
﻿Hello Geeks For Geeks
```

#### 例 3:如除子句所示

在这里，我们将使用 as in except 子句和 try。

## 蟒蛇 3

```
# Python code to demonstrait
# 'as' keyword

# Using alias with try statement
try:
    import maths as mt
except ImportError as err:
    print(err)

# Function showing alias functioning

def geek_Func():
    try:

        # With statement with geek alias
        with open('geek.txt') as geek:

            # reading text with aias
            geek_read = geek.read()

        # Printing our text
        print("Reading alias:")
        print(geek_read)
    except FileNotFoundError as err2:
        print('No file found')

geek_Func()
```

**输出:**

```
No module named 'maths'
No file found
```