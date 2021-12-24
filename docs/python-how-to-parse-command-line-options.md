# Python |如何解析命令行选项

> 原文:[https://www . geesforgeks . org/python-如何解析-命令行-选项/](https://www.geeksforgeeks.org/python-how-to-parse-command-line-options/)

在本文中，我们将讨论如何编写一个 Python 程序来解析命令行中提供的选项(可在 **sys.argv** 中找到)。**参数解析模块**可用于解析命令行选项。

**代码#1:使用 argparse 模块**

```py
'''
Hypothetical command-line tool for searching a 
collection of files for one or more text patterns.
'''
import argparse

parser = argparse.ArgumentParser(description ='Search some files')

parser.add_argument(dest ='filenames', metavar ='filename', nargs ='*')
parser.add_argument('-p', '--pat', metavar ='pattern', 
                    required = True, dest ='patterns', 
                    action ='append', 
                    help ='text pattern to search for')

parser.add_argument('-v', dest ='verbose',
                    action ='store_true', help ='verbose mode')
parser.add_argument('-o', dest ='outfile', 
                    action ='store', help ='output file')
parser.add_argument('--speed', dest ='speed', 
                    action ='store', choices = {'slow', 'fast'},
                    default ='slow', help ='search speed')
args = parser.parse_args()
```

上面提到的程序定义了一个命令行解析器，其用法如下

```py
bash % python3 search.py -h
usage: search.py [-h] [-p pattern] [-v] [-o OUTFILE] 
  [--speed {slow, fast}] [filename [filename ...]]

Search some files

positional arguments:
          filename

optional arguments:
-h, --help           show this help message and exit
-p pattern,    --pat pattern
                 text pattern to search for
-v                   verbose mode
-o OUTFILE           output file
--speed {slow, fast}  search speed
```

观察 print()语句的输出。

**代码:下面的会话显示了数据是如何在程序中显示的。**

```py
bash % python3 search.py foo.txt bar.txt
usage: search.py [-h] -p pattern [-v] [-o OUTFILE]
  [--speed {fast, slow}] [filename [filename ...]]

search.py: error: the following arguments are required: -p/--pat
bash % python3 search.py -v -p spam --pat = eggs 
           foo.txt bar.txt
filenames = ['foo.txt', 'bar.txt']
patterns = ['spam', 'eggs']
verbose = True
outfile = None
speed = slow
```

```py
bash % python3 search.py -v -p spam --pat = eggs 
                 foo.txt bar.txt -o results
filenames = ['foo.txt', 'bar.txt']
patterns = ['spam', 'eggs']
verbose = True
outfile = results
speed = slow
```

```py
bash % python3 search.py -v -p spam --pat = eggs 
            foo.txt bar.txt -o results \--speed = fast
filenames = ['foo.txt', 'bar.txt']
patterns = ['spam', 'eggs']
verbose = True
outfile = results
speed = fast
```

*   **argparse** 模块是标准库中最大的模块之一，有大量的配置选项。上面的代码显示了一个基本的子集，可以使用和扩展来开始。
*   要解析选项，首先创建一个**参数解析器**实例，并使用 **add_argument** ()方法为您想要支持的选项添加声明。
*   在每个 add_argument()调用中，dest 参数指定解析结果将放置的属性的名称。
*   生成帮助消息时使用 **metavar** 参数。
*   action 参数指定与该参数相关联的处理，通常用于存储一个值，或者用于将多个参数值收集到一个列表中。

**代码:**参数将所有额外的命令行参数收集到一个列表中。它被用来制作文件名列表

```py
parser.add_argument(dest = 'filenames',
                    metavar = 'filename', nargs = '*')
```

**代码:**参数根据是否提供了该参数来设置布尔标志

```py
parser.add_argument('-v', dest = 'verbose', 
                    action = 'store_true', 
                    help = 'verbose mode')
```

**代码:**参数接受单个值并将其存储为字符串

```py
parser.add_argument('-o', dest = 'outfile', 
                    action = 'store', help = 'output file')
```

下面的参数规范允许一个参数重复多次，并且所有的值都追加到一个列表中。必需标志意味着该参数必须至少提供一次。