# 检查 if 语句中的多个条件–Python

> 原文:[https://www . geesforgeks . org/check-if 语句中的多个条件-python/](https://www.geeksforgeeks.org/check-multiple-conditions-in-if-statement-python/)

当一个情况导致两个条件并且其中一个应该成立时，在 Python 中使用 If-else 条件语句。

**语法:**

```py
if (condition):
    code1
else:
    code2

```

```py
[on_true] if [expression] else [on_false]
```

**注:**更多信息，请参考 Python 中的[决策(如果，如果..否则，嵌套 if，if-elif)](https://www.geeksforgeeks.org/decision-making-python-else-nested-elif/)

## if 语句中的多个条件

这里我们将研究如何在一个 if 语句中检查多个条件。这可以通过在单个语句中使用“and”或“or”或“BOTH”来实现。

**语法:**

```py
if (cond1 AND/OR COND2) AND/OR (cond3 AND/OR cond4):
    code1
else:
    code2

```

*   **和比较** =为了使其正常工作，所提供的两个条件都应该为真。如果第一个条件为假，编译器不会检查第二个条件。如果第一个条件为真，编译器移动到第二个条件，如果第二个条件为假，则返回 false 到 If 语句。
*   **或比较** =要使其正常工作，任一条件都需要为真。编译器首先检查第一个条件，如果结果为真，编译器运行分配的代码，第二个条件不被计算。如果第一个条件为假，编译器检查第二个条件，如果为真，则运行指定的代码，但是如果也失败，则返回 false 到 If 语句。

以下示例将有助于更好地理解这一点:
**计划 1:** 计划只允许 8-12 岁的孩子进入

```py
age = 18

if ((age>= 8) and (age<= 12)):
    print("YOU ARE ALLOWED. WELCOME !")
else:
    print("SORRY ! YOU ARE NOT ALLOWED. BYE !")
```

**输出:**

```py
SORRY ! YOU ARE NOT ALLOWED. BYE !

```

```py
PROGRAM 2:
```

检查用户同意条款的程序

```py
var = 'N'

if (var =='Y' or var =='y'):
    print("YOU SAID YES")
elif(var =='N' or var =='n'):
    print("YOU SAID NO")
else:
    print("INVALID INPUT")
```

**输出:**

```py
YOU SAID NO

```

**程序 3:** 比较输入的三个数字的程序

```py
a = 7
b = 9
c = 3

if((a>b and a>c) and (a != b and a != c)):
    print(a, " is the largest")
elif((b>a and b>c) and (b != a and b != c)):
    print(b, " is the largest")
elif((c>a and c>b) and (c != a and c != b)):
    print(c, " is the largest")
else:
    print("entered numbers are equal")
```

**输出:**

```py
9  is the largest
```

不仅仅是两个条件，我们可以通过使用‘and’和‘or’来检查更多的条件。
**节目 4:**

```py
a = 1
b = 1
c = 1
if(a == 1 and b == 1 and c == 1):
    print("working")
else:
    print("stopped")
```

**输出:**

```py
working
```