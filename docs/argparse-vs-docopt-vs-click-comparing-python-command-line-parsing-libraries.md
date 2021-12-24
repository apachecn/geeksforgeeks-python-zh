# arg parse VS Docopt VS Click–比较 Python 命令行解析库

> 原文:[https://www . geesforgeks . org/arg parse-vs-docopt-vs-click-comparison-python-命令行-解析-libraries/](https://www.geeksforgeeks.org/argparse-vs-docopt-vs-click-comparing-python-command-line-parsing-libraries/)

在了解 Python 解析库之前，我们必须先了解命令行用户界面。命令行界面 *(CLI)* 为命令行程序提供了一个用户友好的界面，这是开发人员或程序员最喜欢的，他们更喜欢键盘编程，而不是使用鼠标。通过构建命令行界面，用户可以更有效地通过控制台、外壳或终端进行交互。

有很多 Python 库可以构建命令行应用程序，例如 **Argparse** 、 **Docopt** 、 **Click** 、 **Client** 等等。现在，让我们了解更多常用的 Python 库——arg parse、Docopt 和 Click。

## 抱怨吗

Argparse 是一个用户友好的命令行界面。*参数解析*模块解析命令行参数和选项/标志。

**安装:**

安装 argparse 模块的方法有很多，简单的方法是使用 *pip*

```
$ pip install argparse
```

**初始化参数**

```
import argparse
parser=argparse.ArgumentParser(description="Program description")
```

**添加位置/可选参数:**使用 *add_argument()* 我们可以向解析器添加位置/可选参数。

> parser . add _ argument('-parameter name '，'–optional name '，help = ' message ')

这里， *-parameterName* 是一个简写符号。
*–optional name*是可选参数。
*-h–帮助*监控帮助。

**命令行用法**

```
$ python [file].py [command] [options] name
```

**示例:**

## 蟒蛇 3

```
# argparse_example.py

import argparse

if __name__=='__main__':

    #Initialize
    parser=argparse.ArgumentParser(description="Simple calculator")

    #Adding optional parameters
    parser.add_argument('-n1',
                        '--num1',
                        help="Number 1",
                        type=float)

    parser.add_argument('-n2',
                        '--num2',
                        help="Number 2",
                        type=float)

    parser.add_argument('-op',
                        '--operation',
                        help="operator",
                        default="*")

    #Parsing the argument
    args=parser.parse_args()
    print(args)

    #Initialize result to None
    result =None

    #Simple calculator operations
    if args.operation == '+':
        result=args.num1+args.num2

    if args.operation == '-':
        result=args.num1-args.num2

    if args.operation == '/':
        result=args.num1/args.num2

    if args.operation == '*':
        result=args.num1*args.num2

    if args.operation == 'pow':
        result=pow(args.num1,args.num2)

    #Print the result  
    print("Result = " ,result)
```