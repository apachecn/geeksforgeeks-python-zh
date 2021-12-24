# Python:使用 argparse 的键值对

> 原文:[https://www . geesforgeks . org/python-key-value-pair-using-arg parse/](https://www.geeksforgeeks.org/python-key-value-pair-using-argparse/)

Python 中的 **argparse** 模块有助于在命令行环境中创建一个程序，这种方式不仅易于编码，还能改善交互。当用户给程序无效参数时，它还会自动生成帮助和使用信息，并发出错误。

### 使用参数解析模块的步骤:

1.  **创建解析器**:导入 argparse 模块是处理概念的第一种方式。导入之后，您必须创建一个解析器或 ArgumentParser 对象，该对象将存储从 python 命令行传递的所有必要信息。
2.  **添加参数**:下一步是用程序的参数信息填充 ArgumentParser。这意味着对 add_argument()方法的调用。这些信息告诉 ArgumentParser 如何从命令行获取参数，并将它们转换成对象。
3.  **解析参数**:通过 parse_args()解析参数时，会存储并使用步骤 2 中收集的信息。数据最初以字符串格式存储在 sys.argv 数组中。用命令行数据调用 parse_args()首先将它们转换为所需的数据类型，然后调用适当的操作来产生结果。

**键值对使用 Argparse:** 要将参数作为键值对，首先将输入作为一个字符串，使用 python 内置方法*split()***T5】我们将它分成两个单独的字符串，这里表示 Key 及其值。在下一步中，这些被制作成适合字典的形式。**

 **## 蟒 3** 

```py
#importing argparse module
import argparse

# create a keyvalue class
class keyvalue(argparse.Action):
    # Constructor calling
    def __call__( self , parser, namespace,
                 values, option_string = None):
        setattr(namespace, self.dest, dict())

        for value in values:
            # split it into key and value
            key, value = value.split('=')
            # assign into dictionary
            getattr(namespace, self.dest)[key] = value

# creating parser object
parser = argparse.ArgumentParser()

# adding an arguments 
parser.add_argument('--kwargs', 
                    nargs='*', 
                    action = keyvalue)

 #parsing arguments 
args = parser.parse_args()

# show the dictionary
print(args.kwargs)
```