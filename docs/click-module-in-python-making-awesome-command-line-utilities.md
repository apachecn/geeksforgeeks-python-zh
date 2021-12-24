# 点击 Python 中的模块|制作令人敬畏的命令行实用程序

> 原文:[https://www . geesforgeks . org/click-python 中的模块-making-awesome-命令行-utilities/](https://www.geeksforgeeks.org/click-module-in-python-making-awesome-command-line-utilities/)

自从计算机时代的黎明和互联网爆发之前，程序员一直在使用命令行工具在一个交互式外壳中作为与计算机通信的手段。奇怪的是，随着用户界面/UX 技术的进步，很少有人知道也需要创建漂亮的命令行界面。
有没有想过自己创建一个实际上非常用户友好、高效且易于使用的命令行工具？嗯， ***点击*** 就是一个做这个的 Python 包。有很多 Python 包我们可以用来代替*点击*，比如 argparse、docopt 等。，那么我们就先来看看我们为什么要用*点击*。

**为什么*点击*？**

为什么*点击*是这项工作更好的工具，有几个原因。

*   点击可以不受限制地随意组合。
*   它是完全嵌套的。
*   Click 为所有参数和命令提供了强大的信息，因此它可以为整个 CLI 生成统一的帮助页面，并在必要时帮助用户转换输入数据。
*   Click 非常了解什么是类型，如果出现问题，它可以向用户提供一致的错误消息。

**安装:**

```py
pip install click
```

**命令行界面的基本知识:**

根据命令行界面的类型和用途，它可以有多种功能。您可能已经使用了也是命令行界面的 pip。所有 CLi 都具有的一些基本功能包括:

*   一场争论。
*   选项，它是一个可选参数
*   一个标志，这是一个特殊的选项，可以启用或禁用某个功能。最常见的标志之一是——帮助。

**简单程序使用点击**:

```py
# importing click
import click

@click.command()
def main():
    click.echo("This cli is built with click. ")

if __name__=="__main__":
    main()
```

因此，让我们构建一个命令行工具，为参数中提供的名称打印问候语。

**参数解析:** *点击*使用 python 装饰器来解析与函数相关的参数。

```py
@click.command()
@click.argument('name')
def greeting(name):
    click.echo("Hello, {}".format(name))

if __name__=="__main__":
    greeting()
```

> > >`python greet.py Gifoyle`

```py
Hello, Gilfoyle
```

**可选参数:**点击可选择包含标志形式的可选参数。

```py
import click

@click.command()
@click.option('--string', default ='World',
        help ='This is a greeting')
def hello(string):
    click.echo("Hello, {}".format(string))

if __name__=="__main__":
hello()    
```

> > >`python hello.py`

```py
Hello, World
```

> > >`python hello.py --string Dinesh`

```py
Hello, Dinesh
```

**帮助:**制作完美的命令行界面最重要也是最后一步是为我们的代码提供文档。当使用可选参数`--help`时，Click 在命令行中提供了一个漂亮且格式化的帮助文本。它使用函数中指定的 docstring。

```py
import click

@click.command()
@click.argument(‘greeting’)
def cli(greeting):
    '''
    This is the default CLI method.

    Arguments:
            greeting: {string}
    '''

    click.echo(greeting)
    click.echo ("This is a simple cli.")

if __name__=="__main":
    cli()
```

> > >`python cli.py --help`
这是默认的 CLI 方法。

```py

Arguments:
greeting: {string}

Options:
  --string TEXT  Hello
  --help         Show this message and exit.
>>>
```

**错误处理:**错误处理是 CLI 的重要组成部分。您的脚本如何处理和管理错误非常重要，也有助于用户更好地理解错误。

> > > `python cli.py`
这是一个简单的 cli。

> > >`python cli.py hello`

```py
Usage: greet.py [OPTIONS]
Try "greet.py --help" for help.

Error: Got unexpected extra argument (hello)
```