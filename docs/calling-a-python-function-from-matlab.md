# 从 MATLAB 调用 Python 函数

> 原文:[https://www . geesforgeks . org/calling-a-python-function-from-MATLAB/](https://www.geeksforgeeks.org/calling-a-python-function-from-matlab/)

我们可以直接从 MATLAB 中调用 Python 函数和对象。要从 MATLAB 调用 Python 函数，需要安装支持的 Python 版本。MATLAB 支持 2.7、3.6 和 3.7 版本

当您键入 py.command 时，MATLAB 会加载 Python

```
py.modulename.functionname
```

下面的例子展示了如何从 MATLAB 中调用一个用户定义的 Python 函数。

**例 1 :**

调用 Python 函数打印 Hello。
首先，我们将制作一个名为 print.py 的 Python 模块，包含该函数。

## 蟒蛇 3

```
# Python Module - print.py

def printHello():
    return "Hello"
```

现在，在 MATLAB 编辑器中打开一个新文件。验证当前文件夹是否指向 Python 搜索路径。使用下面的代码将当前文件夹添加到 Python 搜索路径中。

## 矩阵实验室

```
if count(py.sys.path, '') == 0
  insert(py.sys.path, int32(0), '');
end
```

调用 Python 函数打印 Hello。

## 矩阵实验室

```
py.print.printHello();
```

**输出:**

```
Hello
```

**例 2 :** 调用 Python 函数得到两个数的和。

首先，我们将创建一个包含函数的 Python 模块名 add.py。

## 蟒蛇 3

```
# Python Module - add.py

def addgivenNumbers( num1, num2):
    sum = num1 + num2
    return sum
```

调用 Python 函数获取两个给定数字的和

## 矩阵实验室

```
py.add.addgivenNumbers(int32(2), int32(3));
```

**输出:**

```
5
```