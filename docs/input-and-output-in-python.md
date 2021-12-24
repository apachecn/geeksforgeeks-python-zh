# Python 中的输入输出

> 原文:[https://www.geeksforgeeks.org/input-and-output-in-python/](https://www.geeksforgeeks.org/input-and-output-in-python/)

在本文中，我们将看到不同的方式，首先我们可以从用户那里获取输入，然后向他们展示输出。

## 如何在 Python 中获取用户输入

有时候，开发人员可能希望在程序的某个点接受用户输入。为此，Python 提供了一个输入()函数。

**语法:**

```
input('prompt')
```

其中 prompt 是一个可选字符串，在输入时显示在字符串上。

### **示例 1: Python 通过消息获取**用户输入

## 蟒蛇 3

```
# Taking input from the user
name = input("Enter your name: ")

# Output
print("Hello, " + name)
print(type(name))
```

**输出:**

```
Enter your name: GFG
Hello, GFG
<class 'str'>
```

**注意:** Python 默认将所有输入作为字符串输入。要将其转换为任何其他数据类型，我们必须显式转换输入。例如，要将输入转换为 int 或 float，我们必须分别使用 [int()](https://www.geeksforgeeks.org/python-int-function/) 和 [float()](https://www.geeksforgeeks.org/float-in-python/) 方法。

### **示例 2:**Python 中的整数输入

## 蟒蛇 3

```
# Taking input from the user as integer
num = int(input("Enter a number: "))

add = num + 1

# Output
print(add)
```

**输出:**

```
Enter a number: 25
26
```

## **如何在 Python 中显示输出**

Python 提供了 [print()](https://www.geeksforgeeks.org/python-output-using-print-function/) 功能，向标准输出设备显示输出。

> ***语法:**打印(值，sep= ' '，end = '\n '，file=file，flush=flush)*
> 
> ***参数:***
> ***值:**任意值，喜欢多少就有多少。打印前将转换为字符串*
> ***sep= '分隔符':**(可选)指定如何分隔对象，如果有多个。默认:' '*
> ***end = ' end ':**(可选)指定在末尾打印什么。默认值:' \n'*
> ***文件:**(可选)具有写方法的对象。默认值:sys.stdout*
> ***刷新:**(可选)布尔值，指定输出是刷新(真)还是缓冲(假)。默认:假*
> 
> ***返回:**返回输出到屏幕。*

### **示例:Python 打印输出**

## 蟒蛇 3

```
# Python program to demonstrate
# print() method
print("GFG")

# code for disabling the softspace feature 
print('G', 'F', 'G')
```

**Output**

```
GFG
G F G

```

在上面的例子中，我们可以看到，在第二个 print 语句的情况下，每个字母之间都有一个空格，print 语句总是在字符串的末尾添加一个新的行字符。这是因为在每一个字符之后都会打印 sep 参数，在字符串的末尾会打印 end 参数。让我们尝试更改这个 sep 和 end 参数。

### 示例:带有自定义 sep 和结束参数的 Python 打印输出

## 蟒蛇 3

```
# Python program to demonstrate
# print() method
print("GFG", end = "@")

# code for disabling the softspace feature 
print('G', 'F', 'G', sep="#")
```

**Output**

```
GFG@G#F#G

```

## 格式化输出

Python 中格式化输出可以通过多种方式完成。让我们在下面讨论它们

### 使用格式化字符串

我们可以使用 [**格式的字符串文字**](https://www.geeksforgeeks.org/formatted-string-literals-f-strings-python/) ，在开引号或三引号之前用 F 或 F 开始一个字符串。在这个字符串中，我们可以在 **{** 和 **}** 之间编写 Python 表达式，这些表达式可以引用变量或任何文字值。

**示例:使用 F 字符串的 Python 字符串格式**

## 蟒蛇 3

```
# Declaring a variable
name = "Gfg"

# Output
print(f'Hello {name}! How are you?')
```

**输出:**

```
Hello Gfg! How are you?
```

### 使用格式()

我们还可以使用 [**format()**](https://www.geeksforgeeks.org/python-format-function/) 函数来格式化我们的输出，使其看起来像样。大括号 **{ }** 用作占位符。我们可以指定变量在输出中出现的顺序。

**示例:使用 format()函数的 Python 字符串格式化**

## 蟒蛇 3

```
# Initializing variables
a = 20
b = 10

# addition
sum = a + b

# subtraction
sub = a- b

# Output
print('The value of a is {} and b is {}'.format(a,b))

print('{2} is the sum of {0} and {1}'.format(a,b,sum))

print('{sub_value} is the subtraction of {value_a} and {value_b}'.format(value_a = a ,
                                                                         value_b = b,
                                                                         sub_value = sub))
```

**输出:**

```
The value of a is 20 and b is 10
30 is the sum of 20 and 10
10 is the subtraction of 20 and 10
```

### 使用%运算符

我们可以使用 [**'%'** 运算符](https://www.geeksforgeeks.org/string-formatting-in-python-using/)。%值被零个或多个元素值替换。使用%的格式类似于 C 编程语言中的“printf”。

*   % d–整数
*   % f–浮动
*   % s–字符串
*   %x – 十六进制
*   % o–八进制

**示例:**

## 蟒蛇 3

```
# Taking input from the user
num = int(input("Enter a value: "))

add = num + 5

# Output
print("The sum is %d" %add)
```

**输出:**

```
Enter a value: 50
The sum is 55
```