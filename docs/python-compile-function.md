# Python 编译()函数

> 原文:[https://www.geeksforgeeks.org/python-compile-function/](https://www.geeksforgeeks.org/python-compile-function/)

**Python compile()函数**以源代码为输入，返回一个准备执行的代码对象，这个代码对象以后可以被 exec()函数执行。

> **语法**编译(源、文件名、模式、标志=0，dont _ inherit = False，optimize=-1)
> 
> **参数:**
> 
> *   **来源**–可以是普通字符串、字节字符串或 AST 对象
> *   **文件名**-这是读取代码的文件。如果不是从文件中读取的，您可以自己命名。
> *   **模式**–模式可以是执行模式、评估模式或单一模式。
> *   **a .**eval–如果源是单个表达式。
> *   **b .**exec–它可以取一个包含 Python 语句、类和函数等的代码块。
> *   **c .**single–如果由单个交互语句组成，则使用该语句
> *   **标记**(可选)和 dont _ inherit(可选)–默认值=0。它注意哪些未来的语句会影响源代码的编译。
> *   **优化(可选)**–告知编译器的优化级别。默认值-1。

## Python 编译()函数示例

### **示例 Python 中的简单编译()示例。**

这里 filename 是 mulstring，exec 模式允许使用 exec()方法，编译方法将字符串转换为 Python 代码对象。

## 蟒蛇 3

```
# Python code to demonstrate working of compile().

# Creating sample sourcecode to multiply two variables
# x and y.
srcCode = 'x = 10\ny = 20\nmul = x * y\nprint("mul =", mul)'

# Converting above source code to an executable
execCode = compile(srcCode, 'mulstring', 'exec')

# Running the executable code.
exec(execCode)
```

**输出:**

```
mul = 200
```

### **示例 2:另一个**演示**正在编译**

## 计算机编程语言

```
# Another Python code to demonstrate working of compile().
x = 50

# Note eval is used for single statement
a = compile('x', 'test', 'single')
print(type(a))
exec(a)
```

**输出:**

```
<class 'code'>
50
```

### 示例 3: Python 从文件编译函数

在这个例子中，我们将使用一些字符串显示方法获取 main.py 文件，然后我们读取文件内容并编译它来编码对象并执行它。

**main.py:**

## 蟒蛇 3

```
String = "Welcome to Geeksforgeeks"
print(String)
```

**Code:** 这里我们将文件内容作为字符串读取，然后编译成一个 Code 对象。

## 蟒蛇 3

```
# reading code from a file
f = open('main.py', 'r')
temp = f.read()
f.close()

code = compile(temp, 'main.py', 'exec')
exec(code)
```

**输出:**

```
Welcome to Geeksforgeeks
```

### **示例 4:使用 eval()** 编译()

这里，当源是单个表达式时，使用 eval。

## 蟒蛇 3

```
# Another Python code to demonstrate
# working of compile() with eval.
x = 50

# Note eval is used for statement
a = compile('x == 50', '', 'eval')
print(eval(a))
```

**输出:**

```
True
```

## **应用:**

1.  如果 Python 代码是字符串形式或者是 AST 对象，并且您想要将其更改为代码对象，则可以使用 compile()方法。
2.  compile()方法返回的代码对象稍后可以使用 exec()和 eval()等方法调用，这些方法将执行动态生成的 Python 代码。