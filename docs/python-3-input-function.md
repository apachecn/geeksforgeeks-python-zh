# Python 3–输入()函数

> 原文:[https://www.geeksforgeeks.org/python-3-input-function/](https://www.geeksforgeeks.org/python-3-input-function/)

在 Python 中，我们使用 **input()** 函数从用户那里获取输入。无论您输入什么作为输入，输入函数都会将其转换为字符串。如果输入整数值，仍然输入()函数，将其转换为字符串。

> **语法:**输入(提示)
> 
> **参数:**
> 
> *   **提示:**(可选)写入标准输出(通常是屏幕)的字符串，没有换行符。
> 
> **返回:**字符串对象

让我们看看例子:

**示例 1:** 从用户处获取输入。

## 蟒蛇 3

```
# Taking input from the user
string = input()

# Output
print(string)
```

**输出:**

```
geeksforgeeks

```

**示例 2:** 通过消息从用户处获取输入。

## 计算机编程语言

```
# Taking input from the user
name = input("Enter your name")

# Output
print("Hello", name)
```