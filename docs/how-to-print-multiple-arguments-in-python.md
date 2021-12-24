# 如何用 Python 打印多个参数？

> 原文:[https://www . geeksforgeeks . org/如何用 python 打印多个参数/](https://www.geeksforgeeks.org/how-to-print-multiple-arguments-in-python/)

参数是调用函数时在函数中传递的值。它们是包含数据或代码的独立项目或变量。在调用期间，每个参数总是被分配给函数定义中的参数。

**例**:简单论证

## 蟒蛇 3

```
def GFG(name, num):
    print("Hello from ", name + ', ' + num)

GFG("geeks for geeks", "25")
```

**输出:**

> 25 岁的极客们，大家好

在没有参数或只有一个参数的情况下调用上述代码会产生错误。

## **变量函数参数**

如上所示，函数有固定数量的参数。在 Python 中，还有其他方法可以定义一个可以接受可变数量参数的函数。
不同形式讨论如下:

*   **Python 默认参数:**函数参数在 Python 中可以有默认值。我们通过使用赋值运算符(=)为参数提供默认值。

**示例:**

## 蟒蛇 3

```
def GFG(name, num="25"):
    print("Hello from", name + ', ' + num)

GFG("gfg")
GFG("gfg", "26")
```

**输出:**

> 你好，来自 gfg，25 岁
> 
> 你好，来自 gfg，26 岁

*   **将其作为元组传递**

## 蟒蛇 3

```
def GFG(name, num):
    print("hello from %s , %s" % (name, num))

GFG("gfg", "25")
```

**输出:**

> 你好，来自 gfg，25 岁

*   **传为字典**

## 蟒蛇 3

```
def GFG(name, num):
    print("hello from %(n)s , %(s)s" % {'n': name, 's': num})

GFG("gfg", "25")
```

**输出:**

> 你好，来自 gfg，25 岁

*   **使用带有数字的新样式字符串格式**

## 蟒蛇 3

```
def GFG(name, num):
    print("hello from {0} , {1}".format(name, num))

GFG("gfg", "25")
```

**输出:**

> 你好，来自 gfg，25 岁

*   **使用带有显式名称的新样式字符串格式**

## 蟒蛇 3

```
def GFG(name, num):
    print("hello from {n} , {r}".format(n=name, r=num))

GFG("gfg", "25")
```

**输出:**

> 你好，来自 gfg，25 岁

*   **连接字符串**T2】

## 蟒蛇 3

```
def GFG(name, num):
    print("hello from " + str(name) + " , " + str(num))

GFG("gfg", "25")
```

**输出:**

> 你好，来自 gfg，25 岁

*   **使用 Python 3.6 中新的 f 字符串格式**

## 蟒蛇 3

```
def GFG(name, num):
    print(f'hello from {name} , {num}')

GFG("gfg", "25")
```

**输出:**

> 你好，来自 gfg，25 岁

*   **使用*args**

## 蟒蛇 3

```
def GFG(*args):
    for info in args:
        print(info)

GFG(["Hello from", "geeks", 25], ["Hello", "gfg", 26])
```

**输出:**

> [《你好，来自》，《极客》，25]
> 
> ['你好'，' gfg '，26]

*   **使用* *夸脱**

## 蟒蛇 3

```
def GFG(**kwargs):
    for key, value in kwargs.items():
        print(key, value)

GFG(name="geeks", n="- 25")
GFG(name="best", n="- 26")
```

**输出:**

> 命名极客
> 
> n–25
> 
> 说出最好的
> 
> n–26