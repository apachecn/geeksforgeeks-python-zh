# Python 中如何使用字符串格式化程序？

> 原文:[https://www . geesforgeks . org/如何使用 python 中的字符串格式化程序/](https://www.geeksforgeeks.org/how-to-use-string-formatters-in-python/)

作为程序的结果而显示的输出应该被组织起来，以便可读和可理解。输出字符串可以使用下面列出的各种方式打印和格式化。

1.  **使用** [**打印()**](https://www.geeksforgeeks.org/python-output-using-print-function/)
2.  **使用格式说明符。**
3.  **采用** [**格式()**](https://www.geeksforgeeks.org/python-format-function/) **法。**
4.  [**使用格式化字符串文字(f-string)**](https://www.geeksforgeeks.org/formatted-string-literals-f-strings-python/) **。**

本文涵盖了上面给出的前三种方法。

## **使用打印()**

**print()** 功能用于显示 Python 中执行的任何消息或进程输出。此功能可用于打印字符串或任何对象。但是，在打印非字符串类型的对象之前，print()会将其转换为字符串。该字符串可以用这个方法本身的参数来格式化，也可以使用本文中介绍的其他方法来格式化。该功能的分隔符参数( **sep** )有助于在打印的每个元素之间显示所需的符号。

**示例:在每次迭代中打印交换，同时按升序排列列表**

## 蟒蛇 3

```
# initialize the list
li = [1, 4, 93, 2, 3, 5]

print("Swaps :")

# loop for arranging
for i in range(0, len(li)):

    for j in range(i+1, len(li)):

        # swap if i>j
        if li[i] > li[j]:
            temp = li[j]
            li[j] = li[i]
            li[i] = temp

            # print swapped elements
            print(li[i], li[j], sep="<--->")

print("Output :", li)
```

**Output**

```
Swaps :
2<--->4
4<--->93
3<--->4
4<--->93
5<--->93
Output : [1, 2, 3, 4, 5, 93]

```

## 使用格式说明符

格式说明符是我们在像 C 编程这样的语言中使用的。Python 没有 C 语言中的 printf()，但这里提供了相同的功能。字符串类重载了模运算符(“%”)来格式化输出。%运算符格式化元组中包含的变量集。如果多个格式说明符被链接，那么第一个说明符作用于元组中的第 0 <sup>个</sup>元素，第二个作用于元组中的第 1 <sup>个</sup>元素，以此类推。下表给出了格式说明符。

<figure class="table">

| **格式说明符** | 

**描述**

 |
| --- | --- |
| %s | 指定了字符串 |
| %c | 指定了单个字符 |
| %d | 指定了整数 |
| %f

 | 指定浮点数。小数点后可以有任意数量的数字 |
| % <space>。 <number>f</number></space> | 指定浮点数。<space>表示打印数字前要追加的空格数。</space><number>表示小数点后的位数。</number> |
| %x / %X | 指定值的十六进制表示形式 |
| %o | 指定值的八进制表示形式 |
| %e / %E | 以指数格式指定浮点数 |
| %g / %G | 类似于%e/%E。仅当指数大于-4 时才指定指数格式 |

</figure>

**示例:**

## 蟒蛇 3

```
# string
st = "This is a string"
print("String is %s" % (st))

# single character
ch = 'a'
print("Single character is %c" % (ch))

# integer
num = 45
print("The number is %d" % (num))

# float without specified precision
float1 = 34.521094
print("The float is %f" % (float1))

# float with precision
float2 = 7334.34819560
print("The float with precision is %.3f" % (float2))

# multiple specifiers in print()
# Hexa decimal representation
print("The hexadecimal form of %d is %x" % (num, num))

# octal representation
print("The octal form of %d is %o" % (num, num))

# exponential form
print("The exponential form of %f is %e" % (float1, float1))

# exponential form with appended space
print("The exponential form of %f is %10.3g" % (float2, float2))

# exponent less than -4 with appended space
float3 = 3.14
print("The exponential form of %.2f is %10.3g" % (float3, float3))
```

**Output**

```
String is This is a string
Single character is a
The number is 45
The float is 34.521094
The float with precision is 7334.348
The hexadecimal form of 45 is 2d
The octal form of 45 is 55
The exponential form of 34.521094 is 3.452109e+01
The exponential form of 7334.348196 is   7.33e+03
The exponential form of 3.14 is       3.14

```

## 使用 format()方法

[format()](https://www.geeksforgeeks.org/python-format-function/) 是 string 类中允许用要格式化的值替换占位符的方法之一。

> **语法:{ }…..{ } .格式(参数)**
> 
> **参数:**
> 
> *   **{ }–**用于存放索引/按键的占位符。允许放置任意数量的占位符。
> *   **参数–**要格式化的值的元组。

参数分为两种类型，即:

*   **位置–**要格式化的对象的索引将被写入占位符中。
*   **关键字****–**参数将为**键=值**类型。这些键将被写在占位符中。

也可以使用此方法执行特定于类型的格式化。日期时间对象、复数也可以使用此方法格式化。

**示例:**

## 蟒蛇 3

```
# complex number
c = complex(5+9j)

# without format() method
print("Without format() - Imaginary :", str(c.imag), " Real :", str(c.real))

# with format() method
print("With format() - Imaginary : {} Real : {}".format(c.imag, c.real))
```

**Output**

```
Without format() - Imaginary : 9.0  Real : 5.0
With format() - Imaginary : 9.0 Real : 5.0

```

可以借助[类](https://www.geeksforgeeks.org/python-classes-and-objects/)和[邓德方法](https://www.geeksforgeeks.org/dunder-magic-methods-python/#:~:text=Dunder%20or%20magic%20methods%20in%20Python%20are%20the%20methods%20having,__%2C%20__repr__%20etc.)来覆盖 format()方法。

## 蟒蛇 3

```
# class for holding person's details
class person:

    # constructor
    def __init__(self, name, age, des):
        self.name = name
        self.age = age
        self.des = des

    # overriding format()
    def __format__(self, f):

        if f == 'name':
            return "I am "+self.name

        if f == 'age':
            return "My age is "+str(self.age)

        if f == 'des':
            return "I work as "+self.des

p = person('nisha', 23, 'manager')
print("{:name}, {:age}".format(p, p))
print("{:des}".format(p))
```

**Output**

```
I am nisha, My age is 23
I work as manager

```

## 使用 f 字符串

这种方法是在 Python 3.6 版本中引入的。这比使用格式说明符或 format()方法容易得多。f 字符串是在运行时计算的表达式，由 **__format__()方法**格式化。使用 f-string 格式化字符串时，格式化表达式必须用引号括起来，前面加**“F”/“F”**。

> 语法: **f " <文本>{占位符} <文本>或 F" <文本>{占位符} <文本> "**

**例** **1** :

姓名和年龄是变量。通过将变量放在适当的占位符中，可以在 f-string 的帮助下格式化和打印它们。占位符只是文本中的大括号。

## 蟒蛇 3

```
name = "Rinku"
age = 20

print(f"Hi! my name is {name} and my age is {age}")
```

**Output**

```
Hi! my name is Rinku and my age is 20

```

**例 2:**

表达式也可以使用这个 f-string 方法来计算和显示。

## 蟒蛇 3

```
a = 5
b = 6

print(F"Addition : {a+b}")
print(F"Subtraction : {a-b}")
print(F"Multiplication : {a*b}")
print(F"Division without roundoff : {a/b}")
print(F"Division with roundoff : {round(a/b,3)}")
```

**Output**

```
Addition : 11
Subtraction : -1
Multiplication : 30
Division without roundoff : 0.8333333333333334
Division with roundoff : 0.833

```

**例 3:**

甚至可以从 f 字符串占位符中调用函数。在占位符中定义并调用了一个函数来计算表达式**a<sup>2</sup>+3b<sup>2</sup>+ab**。

## 蟒蛇 3

```
# f function to evaluate expression
def exp_eval(a, b):
    ans = (a*a)+(3*(b*b))+(a*b)
    return ans

# values to be evaluated
a = 2
b = 4

# formatting
print(f"The expression a**2+3b**2+(a*b) = {exp_eval(a,b)}")
```

**Output**

```
The expression a**2+3b**2+(a*b) = 60

```