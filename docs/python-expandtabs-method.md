# Python 中的 expandtabs()方法

> 原文:[https://www.geeksforgeeks.org/python-expandtabs-method/](https://www.geeksforgeeks.org/python-expandtabs-method/)

expandtabs 是 Python 3 中 Strings 中指定的方法。

有时，需要指定字符串中的空间，但剩余的空间量是不确定的，取决于环境和条件。对于这些情况，需要一次又一次地修改字符串是一项繁琐的任务。因此 python 在其库中有“ **expandtabs()** ”，它指定了字符串中要用“\t”符号替换的空间量。

> 语法: **expandtabs(space_size)**
> 
> **参数:**
> **space_size :** 指定字符串中要用“\t”符号替换的空间。默认情况下，空格为 8。
> 
> **返回:**返回修改后的字符串，制表符由空格代替。

**代码#1 :** 代码演示 expandtabs()

```
# Python3 code to demonstrate
# working of expandtabs()

# initializing string 
str = "i\tlove\tgfg"

# using expandtabs to insert spacing
print("Modified string using default spacing: ", end ="")
print(str.expandtabs())

print("\r")

# using expandtabs to insert spacing
print("Modified string using less spacing: ", end ="")
print(str.expandtabs(2))

print("\r")

# using expandtabs to insert spacing
print("Modified string using more spacing: ", end ="")
print(str.expandtabs(12))

print("\r")
```

输出:

```
Modified string using default spacing: i       love    gfg

Modified string using less spacing: i love  gfg

Modified string using more spacing: i           love        gfg

```

**例外:**
使用这种方法的例外是，如果我们想决定我们需要的空间的精确精度，它不接受浮点数。

**代码#2 :** 代码演示 expandtabs()异常

```
# Python3 code to demonstrate
# exception of expandtabs()

# initializing string 
st = "i\tlove\tgfg"

# using expandtabs to insert spacing
try:
    print("Modified string using default spacing: ")
    print(st.expandtabs(10.5))

except Exception as e:
    print("Error !! The error occurred is :")
    print(str(e))
```

输出:

```
Modified string using default spacing: 
Error !! The error occurred is :
integer argument expected, got float

```

**应用程序:**
有许多可能的应用程序可以使用它，例如文本格式或用户需求不断变化的文档。