# Python 中如何使用 NamedTuple 和 Dataclass？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 中的名称解析和数据类/](https://www.geeksforgeeks.org/how-to-use-namedtuple-and-dataclass-in-python/)

我们在编码时都不止一次地使用过 [类和对象](https://www.geeksforgeeks.org/python-classes-and-objects/) 。但是你有没有想过如何创建一个除了我们都学过的简单方法之外的类。不要担心，在本文中，我们将介绍这些替代方法。在 Python 中，有两种可选的方法来构造类。

*   [命名双](https://www.geeksforgeeks.org/namedtuple-in-python/)
*   [数据类](https://www.geeksforgeeks.org/data-classes-in-python-an-introduction/)

首先，让我们用简单的方法创建一个类。让我们创建一个类事务，其中每个支付事务都有一个发送者、一个接收者、日期和金额。

**示例:**

## 计算机编程语言

```py
class Transaction:

    def __init__(self, amount, sender, receiver, date):
      self.amount = amount
      self.sender = sender
      self.receiver = receiver
      self.date = date
```

这是非常直接的，但是让我们诚实地说，对于我们这些懒惰的开发人员来说，这是很多代码。现在，这就是命名图的来源。

## 使用名称对

[命名元组](https://www.geeksforgeeks.org/namedtuple-in-python/)本质上是 Python 内置元组数据类型的扩展。Python 的元组是一种简单的数据结构，用于对不同类型的对象进行分组。它的定义特征是不可变的，即一个对象在创建后其状态不能被修改。

我们将从收集包开始。这个包提供了 Python 通用内置类型的替代，如 dict、list、set 和 tuple。创建一个名为的对象和创建类一样简单。

## 蟒蛇 3

```py
import collections

Transaction = collections.namedtuple('Transaction',
                                     ['sender', 'amount',
                                      'receiver', 'date'])

# Creating object
record = Transaction(sender="Aryaman",
                     receiver="Ankur",
                     date="2020-06-18",
                     amount=1.0)

print(record)
print(record.receiver)
```

**输出:**

> 交易(发送方='Aryaman '，金额=1.0，接收方='Ankur '，日期='2020-06-18 ')
> 
> 锚

## 使用数据类

DataClass 可能是自 Python 3.7 以来引入的新功能。它被用作装饰器。它在幕后所做的就是为我们实现 __init__，__repr_，等等。

**示例:**

## 蟒蛇 3

```py
from dataclasses import dataclass

@dataclass
class Transaction:
    sender: str
    receiver: str
    date: str
    amount: float

# Creating object
record = Transaction(sender="Aryaman",
                     receiver="Ankur",
                     date="2020-06-18",
                     amount=1.0)

print(record)
print(record.receiver)
```

**输出:**

> 交易(发送方='Aryaman '，接收方='Ankur '，日期='2020-06-18 '，金额=1.0)
> Ankur

NamedTuple 的行为像元组，而 DataClass 的行为更像普通的 Python 类，因为默认情况下，属性都是可变的，只能通过名称访问，而不能通过索引访问。